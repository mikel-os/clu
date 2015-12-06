# Uniform Version Numbering

>Copyright &copy; 2015 Mikel Cazorla Pérez.

>Esta obra está sujeta a la licencia Reconocimiento 4.0 Internacional de Creative Commons. Para ver una copia de esta licencia, visite http://creativecommons.org/licenses/by/4.0/.

#### 0.0.0.0

To avoid improvising on the fly (and minimize dependency hell), this spec has
been written here, and will be extended in the future if were necessary.

    A.X.Y.Z

    A Base number
      X Gen number
        Y Minor number
          Z Patch number

(Note: provisional names)

#### Common criteria

This spec doesn't limit the numbers max value, but their range must be inside the positive integers (including zero). Leading zeros not allowed.

Some valid versions are:

    0.0.1.0
    1.9.2.57
    1.10.0.0

Some valid numbers are:

    0
    9
    10
    514

Some invalid numbers are:

    00
    07
    0...01
    -12

In general, a version is "greater" than other if the leftmost different number between both is greater in the former.

    1.10.0.0 > 1.9.2.57 > 0.0.1.0

When a number change, all the number on its right are reseted to zero in that version.

    1.9.2.57

    If X (9) change, the new version will be "1.10.0.0".
    No matter if a bug was fixed, Z is reseted anyway.
    No matter if a minor feature was added, Y is reseted too.
    (But I don't recommend make so many changes in one step).

#### Explicit criteria to fix a bug in a previous version

But to allow fix bugs backwards, at least Z can be increased in a A.X.Y version after a greater A.X.Y has been created.

    Suppose 1.9.2.57 and 1.10.0.0 exist.
    Then it is allowed create 1.9.2.58 if were necessary.

If that happens, every version of the same A.X subfamily greater than the fixed version should be fixed too with a new Z version. Since there is not guaranteed at all that the greater versions have been fixed.

    If 1.9.3.0 exist too and have the same bug, you should create 1.9.3.1.

This means some features, fixes, changes and even bugs evolve from the immediate predecessor of a version, but a version can inherit others from an older version due this backward progression.

    Note: do not abuse this power.

 It would be nice if you care of you fellows (and yourself) and make a comment to note both circumstances, even if it isn't required by this specs.

#### Early versions

The first version should be 0.0.0.0 for consistency. Although negative numbers are forbidden, you can imagine that A = -1 is a way to describe a non-existent state. When A change to 0, the existent state "emerges". This way, it's obvious the first A = 2 will be 2.0.0.0 (see the meaning of pair vs odd values for A in "**_When to increase a number_**").

There is no reason to use a different criteria for the naming of A = 0 family versus A > 0 family. Anyway this spec doesn't impose you nothing, 0.0.1.0 it's ok (just discouraged).

#### When to increase a number

1. Z increment means a bug was fixed.
2. Y increment means a "feature" was added in a backward compatible manner.
3. X increment means backward compatibility was broken.
4. A mod 2 = 1 families are feature complete versions, and its A - 1 respective families are their "in development" counterparts. Every pair of families **represent different programs** relative to any other pair, but may (and probably) share code, and represent too a single evolutionary development.

So, A = 0 is the first not complete family of a program (but X, Y and Z can work as usual). Then, the first feature complete version is 1.0.0.0, and once is necessary broke brutally backward compatibility to update the program for changing times, as features are removed and added to create the new program, A is set to and remain as "2".

As soon the new version is full featured, A change to "3", and so. Note that, as long A = (0 or 1) and A = (2 or 3) belong to different programs you probably need different repositories (is your choice). Moreover, if the new program has been conceived as the successor of but is not "genetically" linked to the first one, maybe you should use another name. Use your mileage.

The good (?) part is even if you try to do the ugliest set of decisions, the naming allows you achieve your goal as long keep every program out of the hair of the others.

A truly good rationale for A number is separate the "completion/incompletion feeling" from X between X = 0 and X = 1, to avoid couple it to its real job (see the list above), which can prevent carry it out (see "**_Early versions_**" section).

#### All other considerations secondary. Metadata expendable.

For simplicity, is not allowed A.X.Y.Z identical parts in two different versions.

Allow "surnames" to distinguish versions would require specify the order of precedence in that cases, but only numerical values could be sorted consistently.

If you have to make a new version, updating X, Y and Z should be enough.

If you want combine the number to be read by a human or program, it's advisable put the number at the beginning of the string and be differentiated clearly from the rest of the data. But the version number is just a A.X.Y.Z number, no more.

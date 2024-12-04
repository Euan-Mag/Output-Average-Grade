using System;

class Program {
  // @@@ devTEST (TESTING PURPOSES ONLY) @@@
  static class devTest {
    public static bool isOn = false; //switch to "true" to turn on testing mode

    //Mark lines of code related to devTest beyond this comment with "---[START OF DT]---" (at start) and "---[END OF DT]---" (at end)
    //Mark outputs that are displayed by devTest.isOn being true as "[DT]"
  }

  // @@@ MAIN @@@
  public static void Main (string[] args) {
    //---[START OF DT]---
    if (devTest.isOn) {
      Console.WriteLine("===[DT] devTest (DT) is ACTIVATED==="); // [DT]
    }
    //---[END OF DT]---

    student student = new student();

    //## getting the name ##
    Console.Write("Type the student's name: ");
    student.StudentName = Console.ReadLine();

    //---[START OF DT]---
    if (devTest.isOn) {
      Console.WriteLine($"{Environment.NewLine} [DT] student's name is: {student.StudentName}{Environment.NewLine}"); // [DT] | "Environment.NewLine" makes a new line
    }
    //---[END OF DT]---

    /*## getting each subject's grade, in which all
    will be stored as an array ##*/
    Console.Write("Type the number of subjects the student studies: "); //used in conjunction with "int numOfSubjects..."
    int numOfSubjects = Convert.ToInt32(Console.ReadLine()); //all user inputs are string, so "Convert.ToInt32" converts it into an integer.
    int[] grades = new int[numOfSubjects]; //creates an array with the same number of indexes as the value of "numOfSubject"
    Console.WriteLine(); //for separating only

    int[] gradesArray = getGrades(numOfSubjects, grades);

    student.grades = gradesArray; //assigns the value of "gradesArray" to the student's "grades" attribute

    //## getting the average grade (as a rounded integer) and assigning it to "finalGrade" attribute within "student" class
    int studentAverageGrade = findAverageGrade(student.grades);
    student.finalGrade = studentAverageGrade;

    //## outputting the student's name, their subjects' grades (as an array), and the average final grade (10 lines of code below)
    Console.WriteLine($"----- ----- -----"); //for separating only

    Console.WriteLine($"Student's name is: {student.studentName}");

    Console.Write("Student's grades are: ");
    Console.WriteLine("[{0}]", string.Join(", ", student.grades));

    Console.WriteLine($"Student's final average grade is: {student.finalGrade}");

    Console.WriteLine($"----- ----- -----"); //for separating only
  }

  // @@@ FUNCTION(S) @@@
  //!!function below gets each grade's score (as a percentage) and assigns it to its "gradeForThisSubject" array's respective index
  static int[] getGrades(int numOfSubjects, int[] grades) {
    for (int i=0; i<numOfSubjects; i++) {
      Console.Write($"Type the grade as a percentage (don't type '%') the student received in subject {i+1}: "); //"i+1" ensures that, if i is 0, then it won't output "Type the grade the student received in subject 0: "
      int gradeForThisSubject = Convert.ToInt32(Console.ReadLine());

      grades[i] = gradeForThisSubject;
    }

    //---[START OF DT]---
    if (devTest.isOn) {
      Console.WriteLine($"{Environment.NewLine} [DT] subject scores goes as follows:"); //[DT]
      for (int i=0; i<numOfSubjects; i++) {
        Console.WriteLine($"--[DT] subject {i+1} (i.e. {i} before being incremented): {grades[i]}"); //[DT]
      }
      Console.WriteLine();  //[DT] | makes a new line so "Environment.NewLine" is unnecessary
    }
    //---[END OF DT]---

    return grades;
  }

  //!!function below returns the average grade, which is calculated by adding up all of the scores in the "grades" parameter, then divides it by the number of indexes in the same array
  static int findAverageGrade(int[] grades) {
    //CONTINUE HERE
    int totalGradeScores = 0;

    //assigning the "totalGradeScores" variable the value of the sum of all the elements within the "grades" parameter (3 lines of code below)
    for (int i=0; i<grades.Length; i++) { //will essentially be repeated 3 lines (including '//---[START OF DT]---' comment) below
      //---[START OF DT]---
      if (devTest.isOn) {
        for (int gradeScore=0; i<grades.Length; gradeScore++) {
          Console.WriteLine($"[DT] 'totalGradeScores' array before being added by 'grades[{gradeScore}]' (value: {grades[gradeScore]}: {totalGradeScores}"); // [DT]
        }
        Console.WriteLine();  //[DT] | makes a new line so "Environment.NewLine" is unnecessary
      }
      //---[END OF DT]---

      totalGradeScores += grades[i];
    }

    //assigning the "averageGrade" variable the mean grade, which is calculated by dividing the "totalGradeScores" variable by the length of the "grades" parameter (1 line of code below)
    double averageGrade = (double) totalGradeScores / grades.Length;

    //---[START OF DT]---
    if (devTest.isOn) {
      Console.WriteLine($"[DT] value of 'totalGradeScores': {totalGradeScores}"); //[DT]
      Console.WriteLine($"[DT] value of 'grades.Length': {grades.Length}"); //[DT]

      Console.WriteLine($"[DT] value of 'averageGrade': {averageGrade}"); //[DT]
      Console.WriteLine($"[DT] value of 'averageGrade' when rounded: {Math.Round(averageGrade)}"); //[DT]
      Console.WriteLine();  //[DT] | makes a new line so "Environment.NewLine" is unnecessary
    }
    //---[END OF DT]---

    return Convert.ToInt32(Math.Round(averageGrade)); //"Convert.ToInt32" prevents this error from being displayed while editing code: 'Cannot implicitly convert type 'double' to 'int'. An explicit conversion exists (are you missing a cast?)'; Math.Round() rounds its passed arguments to the nearest integer
  }

  // @@@ CLASS OF STUDENT @@@
  class student {
    public string studentName;
    public int[] grades;
    public int finalGrade;

    //because of the properties (the 4 lines of code below), this will allow the "studentName" attribute to have the value of "student.StudentName"
    public string StudentName {
      get {return studentName;}
      set {studentName = value;}
    }
  }
}

package IsfarMethodMadnessFinal;

public class testFile {

    public static void main(String[] args) {
        System.out.println("Is it a palindrome? True or false? " +IOshirLib.isPalindrome("racecar"));                    //This is to check if a word is a palindrome.
        System.out.println("The date is: " + IOshirLib.dateStr("01/08/1999"));                                          //This changes the format of the date from month-day to day-month.
        System.out.println("The sum is " + IOshirLib.sumIntegers(4));                                                       //This takes the sum of integers from 0 to some integer value.
        System.out.println("The final word is " + IOshirLib.cutOut("catatonic cat", "cat"));                    //This takes allows you to remove a subset of letters from a particular word.
        System.out.println("End: " + IOshirLib.multiplicationTable(4, 5));                                              //This takes one integer and makes a table of products of that specific integer and other numbers up to a certain value.
        System.out.println(IOshirLib.quadSolver(1,1,1));                                                             //This uses the quadratic formula to find the roots of a quadratic equation.
    }
}
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
package IsfarMethodMadnessFinal;

public class IOshirLib {                                            //String Method1
    public static boolean isPalindrome(String input) {
        String pal = "";                                            //sets an empty string for the palindrome
        int i = input.length();                                     //sets a variable "i" to the length of the inputted word.
        while (i > 0) {                                             //while "i" is greater than zero, "pal" will update itself by taking the last characters of the input and adding it to "pal."
            pal = pal + input.substring(i - 1, i);
            i = i - 1;
        }
        if (pal.equals(input)) {                                    //if the two words are the same, then the code will return true
            return true;                                            //if they're not the same, then it will return false.
        } else {
            return false;
        }
    }

    public static String dateStr(String input2) {                  //String Method2
        String first = "";                                         //There are 3 empty strings created.
        String second = "";
        String third = "";
        first = input2.substring(3, 5) + "-";                      //The first string will be the "day" section of the date.
        second = input2.substring(0, 2) + "-";                     //The second string will be the "month" section of the date.
        third = input2.substring(6, 10);                           //The third string will be the "year string".
        return first + second + third;                             //It returns a concatenation of all the 3 strings.
    }

    public static int sumIntegers(int n) {                         //Math Method1
        int sum = 0;                                               //An integer "sum" is initialized to 0.
        for (int i = 1; i <= n; i++) {                             //When an integer "i" (which is initially 1) is less than "n" (the input), the sum would be added by the current "i", which increases every loop.
            sum = sum + i;
        }
        return sum;                                                //The final sum is returned.
    }

    public static String cutOut(String mainStr, String subStr)     //String Method3
    {                                                              //This basically takes the first part of a given word to the beginning of the removed word and concatenates with the end of the removed word to the end of the given word.
        String output = "";
        output = mainStr.substring(0, mainStr.indexOf(subStr)) + mainStr.substring(mainStr.indexOf(subStr) + subStr.length(), mainStr.length());
        return output;
    }

    public static int multiplicationTable(int ib, int ir)          //Math Method 2
    {
        int product = 0;                                           //A product integer is set to 0.
        for (int index = 0; index <= ir; index++)                  //An index is created at 0, and while the index is less than the range, the base will be mulitplied by the index, which increases by 1 every loop.
        {
            product = ib * index;
            System.out.println(product + " ");
        }
        return product;                                            //This returns the last product.
    }

    public static double quadSolver(double a, double b, double c)
    {
        double p1 = -1 * b;                                        //Extra credit: This method basically takes the quadratic formula and inputs a, b, and c to get the two roots.
        double p2 = (b * b) - (4 * a * c);                         //If the square root portion of the equation is less than 0, then it will determine the roots to be imaginary.
        double p3 = java.lang.Math.sqrt(p2);
        if (p3 < 0)
        {
            System.out.println("The roots are imaginary.");
        }
        else
            {
            double p4a = (p1 - p3) / (2 * a);
            double p4b = (p1 + p3) / (2 * a);
            System.out.println(p4a);
            System.out.println(p4b);
             }
        return p1;
    }
}




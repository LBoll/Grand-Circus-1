using System;
namespace NumberApplication
{
    class Number
    {
        static void Main(string[] args) {
            int num1 = getNum();
            int num2 = getNum();
            
            // Get sum of ones digits
            int ones = num1 % 10 + num2 % 10;
            num1 /= 10;
            num2 /= 10;
            // Get sum of tens digits
            int tens = num1 % 10 + num2 % 10;
            num1 /= 10;
            num2 /= 10;
            // Get sum of hundreds digits
            int hundreds = num1 % 10 + num2 % 10;
            if (ones == tens && ones == hundreds) {
                Console.WriteLine("True");
            } else {
                Console.WriteLine("False");
            }
            Console.WriteLine("Press any key to continue");
            Console.ReadKey();
        }

        /**
         *  Get user's input
         *  
         *  Returns a valid 3 digit number
         */
        static int getNum() {
            int val = -1;
            while (val < 100 || val > 999) {
                Console.Write("Enter 3 digit number: ");
                // Try to convert input to int
                try {
                    val = Convert.ToInt32(Console.ReadLine());
                } catch (Exception e) {
                    // User did not input a number
                    Console.WriteLine("Invalid number");
                    val = -1;
                }
            }
            return val;
        }
    }
}

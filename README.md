









using System;



using System.IO;


namespace SpellCheckerTask

{

    class Program
    
    {
        static void Main(string[] args)
        {
            // Read words from file - done up to 5 wors
            
            string[] allWords = File.ReadAllLines("WordsFile.txt");

            string word1 = allWords[0].ToLower();
            string word2 = allWords[1].ToLower();
            string word3 = allWords[2].ToLower();
            string word4 = allWords[3].ToLower();
            string word5 = allWords[4].ToLower();
            Console.Write("Enter one word: ");
            string inputWord = Console.ReadLine().ToLower();

            if (inputWord == word1 || inputWord == word2 || inputWord == word3 || inputWord == word4 || inputWord == word5)
            {
                Console.WriteLine("Correct spelling!");
            }
            else
            {
                Console.WriteLine("Incorrect spelling.");
            }
            

            // Ask for a sentence
            Console.Write("Please Enter a sentence: ");
            string sentence = Console.ReadLine().ToLower();
            string[] sentenceWords = sentence.Split(' ');

            int totalWords = 0;
            int correctWords = 0;

            foreach (string word in sentenceWords)
            {
                totalWords++;

                if (word == word1 || word == word2 || word == word3 || word == word4 || word == word5)
                {
                    correctWords++;
                }
            }

            // Display the score thry got for the test
            double score = (double)correctWords / totalWords * 100;
            Console.WriteLine("\nCorrect words: " + correctWords + "/" + totalWords);
            Console.WriteLine("Spelling Score: " + score + "%");
        }
    }
}

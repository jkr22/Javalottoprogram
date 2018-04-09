package Lotteryprogram;
import javax.swing.JOptionPane;
public class Lotteryprogram
{
    public static void main(String[] args)
    {
            Newlottery lottoprogram = new Newlottery();
            String playagain = "yes";
            while (playagain.equalsIgnoreCase("yes"))
            {
                lottoprogram.User_pick_numbers();
                lottoprogram.print_picks();
                lottoprogram.jackpot_winner();
                lottoprogram.check_winner();
                lottoprogram.Write_data();
                lottoprogram.count_matches();
                lottoprogram.total_matches();
                lottoprogram.percent_matches();
                lottoprogram.money_won();

                //ask to play again
                playagain = JOptionPane.showInputDialog(null, "Do you want to play again, Yes/No?", "Input Dialog", JOptionPane.QUESTION_MESSAGE);

            }
            lottoprogram.print_results();
            System.exit(0);
        }
    }

    class Newlottery
    {
        int total = 0;
        double total_winnings;
        int count_zero_match = 0,count_one_match = 0,count_two_match = 0,count_three_match = 0,count_full_match = 0;
        int percent_zero_match = 0,percent_one_match = 0, percent_two_match = 0, percent_three_match = 0, percent_full_match = 0;
        double zero_match = 0;
        double one_match = 100;
        double two_match = 1000;
        double three_match = 50000;
        double full_match = 500000;
        int[] userpicks = new int[4];
        int[] comppicks = new int[4];
        int i;
        int j, c;
        int match = 0;


         void User_pick_numbers()

        {
            String value, output;
            int temp = 0, enter = 0, duplicate = 0;
            for (i = 0; i <= 3; ++i) {
                enter = 0;
                duplicate = 0;
                while ((enter == 0) && (duplicate == 0)) {
                    output = "Please pick 4 numbers between 1 and 40" + "\n" + "Number " + (i + 1) + ">";
                    value = JOptionPane.showInputDialog(null, output, "", JOptionPane.QUESTION_MESSAGE);
                    temp = Integer.parseInt(value);
                    //check between the number 1 and 40
                    while ((temp > 40) && (temp < 1)) {
                        JOptionPane.showMessageDialog(null, "Number must be between 1 and 40", "Output:", JOptionPane.INFORMATION_MESSAGE);
                        enter = 0;
                        output = "Please pick 4 numbers between 1 and 40" + "\n" + "Number " + (i + 1) + ">";
                        value = JOptionPane.showInputDialog(null, output, "", JOptionPane.QUESTION_MESSAGE);
                        temp = Integer.parseInt(value);
                    }
                    enter = 1;
                    //check to make sure there aren't any duplicate inputs
                    duplicate = 1;
                    for (c = 0; c <= i; ++c) {
                        if (temp == userpicks[c]) {
                            duplicate = 0;
                        }
                    }
                    if (duplicate == 0)
                        JOptionPane.showMessageDialog(null, "Number is already picked, please input a different number", "Output:", JOptionPane.INFORMATION_MESSAGE);
                    if ((enter == 1) && (duplicate == 1))
                        userpicks[i] = temp;
                    else {
                        enter = 0;
                        duplicate = 0;
                    }
                }
                userpicks[i] = temp;
            }
        }

         void print_picks() {
            String Player = "Your Lottery picks are: " + "\n";
            for (int i = 0; i <= 3; ++i) {
                Player += userpicks[i] + "-";
            }
            Player = Player.substring(0, Player.length() - 1);
            JOptionPane.showMessageDialog(null, Player, "Output:", JOptionPane.INFORMATION_MESSAGE);

        }

         void jackpot_winner() {
            int ctemp, cduplicate = 0;
            for (j = 0; j <= 3; ++j) {
                cduplicate = 0;
                while (cduplicate == 0) {
                    ctemp = (int) Math.round(Math.random() * 40) + 1;
                    cduplicate = 1;
                    for (c = 0; c <= j; ++c) {
                        if (ctemp == comppicks[c]) {
                            cduplicate = 0;
                        }
                    }
                    if (cduplicate == 1)
                        comppicks[j] = ctemp;
                }
            }
            String Jackpot = "The computer lottery numbers are: " + "\n";
            for (j = 0; j <= 3; ++j) {
                if (j == 3)
                    Jackpot = Jackpot + comppicks[j];
                else
                    Jackpot = Jackpot + comppicks[j] + "-";
            }

            JOptionPane.showMessageDialog(null, Jackpot, "Output:", JOptionPane.INFORMATION_MESSAGE);
        }

         void check_winner()

        {

            for (int i = 0; i <= 3; ++i) {
                for (int j = 0; j <= 3; ++j) {
                    if (userpicks[i] == comppicks[j]) {
                        match = match + 1;
                    }
                }
            }
        }

         void Write_data() {
            String print = "";

            for (int i = 0; i <= 3; ++i) {
                if (i == 3) {
                    print = print + userpicks[i] + "\n";
                } else {
                    print = print + userpicks[i] + "-";
                }
            }

            for (j = 0; j <= 3; ++j) {
                if (j == 3)
                    print = print + comppicks[j] + "\n";
                else
                    print = print + comppicks[j] + "-";
            }

            if (match == 0) {
                print = print + "There is no match" + "\n";
                print = print + "No winning: " + zero_match;
            } else if (match == 1) {
                print = print + "There is 1 match" + "\n";
                print = print + "Congrats, you won: " + one_match;
            } else if (match == 2) {
                print = print + "There are 2 matches" + "\n";
                print = print + "Congrats, you won: " + two_match;
            } else if (match == 3) {
                print = print + "There are 3 matches" + "\n";
                print = print + "Congrats, you won: " + three_match;
            } else if (match == 4) {
                print = print + "All the numbers matched" + "\n";
                print = print + "Congrats, you won the jackpot!!!!: " +full_match;
            }
            JOptionPane.showMessageDialog(null, print, "Output:", JOptionPane.INFORMATION_MESSAGE);
        }
        void count_matches()
        {
            if(match==0)
                count_zero_match=count_zero_match+1;
            else
                if(match==1)
                    count_one_match=count_one_match+1;
            else
                if(match==2)
                    count_two_match=count_two_match+1;
            else
                if(match==3)
                    count_three_match=count_three_match+1;
            else
                if(match==4)
                    count_full_match=count_full_match+1;
        }
        void total_matches()
        {
            total=count_zero_match+count_one_match+count_two_match+count_three_match+count_full_match;
        }
        void percent_matches()
        {
            if(match==0)
                percent_zero_match=((count_zero_match*100)/(total));
            else
                if(match==1)
                    percent_one_match=((count_one_match*100)/(total));
            else
                if(match==2)
                    percent_two_match=((count_two_match*100)/(total));
            else
                if(match==3)
                    percent_three_match=((count_three_match*100)/(total));
            else
                if(match==4)
                    percent_full_match=((count_full_match*100)/(total));
        }
        void money_won()
        {
            total_winnings= (count_one_match*one_match)+(count_two_match+two_match)+(count_three_match+three_match)+(count_full_match*full_match);

        }


         void print_results()
         {
            System.out.println("Overall Calculations");
            System.out.println("Number of games played= " + total);
            System.out.println("Number of times zero numbers were matched= " + count_zero_match);
            System.out.println("Percent zero numbers were matched= " + percent_zero_match);
            System.out.println("Number of times one numbers were matched= " + count_one_match);
            System.out.println("Percent one number was matched= " + percent_one_match);
            System.out.println("Number of times two numbers were matched= " + count_two_match);
            System.out.println("Percent two numbers were matched= " + percent_two_match);
            System.out.println("Number of times three numbers were matched= " + count_three_match);
            System.out.println("Percent three numbers were matched= " + percent_three_match);
            System.out.println("Number of times all numbers were matched= " + count_full_match);
            System.out.println("Percent all numbers were matched= " + percent_full_match);
            System.out.println("Total winnings= " + total_winnings);
         }
    }

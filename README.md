# Contiguous-Ones-Challenge

In the magical realm of CodeLand, your wise teacher has presented you with a captivating challenge to test your programming skills. You have been given a binary string X, a special sequence made up of only ‘0’s and ‘1’s.
Your mission is to gather all the ‘1’s together, forming a perfect block of happiness without any ‘0’s interrupting their unity. To achieve this, you possess a powerful ability: you can pick any index i (where 0 < i < n - 1, and n is the length of the string) and reverse the portion of the string from the start to that index.
Now, the quest is clear: determine the minimum number of moves required to bring all the ‘1’s together in a contiguous block. Are you ready to embark on this coding adventure and prove your prowess?

Input
The line of the input contains a single integer N.
The second line of the input contains a string of length N.

Constraints
1 ≤ N ≤ 105
String contains only the characters '0' and '1'.
Output
Print the minimum number of moves you will have to make to accomplish the given task.

import java.io.*; // for handling input/output
import java.util.*; // contains Collections framework

// don't change the name of this class
// you can add inner classes if needed

class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        String s = sc.next();
        int cnt = 0;
        for (int i = 1; i < n; i++) {
            if (s.charAt(i - 1) == '0' && s.charAt(i) == '1') {
                cnt++;
            }
        }
        int ans = (s.charAt(0) == '0') ? 2 * cnt - 2 : 2 * cnt - 1;
        ans = Math.max(0, ans);
        System.out.println(ans);
    }
}

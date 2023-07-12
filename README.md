# coding
about my first code
this is my code that i have successfully runned on intellij hope you all will appreciate it. thanks..

 //  SUM OF ARRAYS --->> THIS IS MY CODE FOR THE ADDITION OF TWO ARRAYS::


    public static void main(String[] args) {
        Scanner scn = new Scanner(System.in) ;

        int size1 = scn.nextInt();
        int[] arr1 = new int[size1];
        for (int i = 0; i < arr1.length; i++) {
            arr1[i] = scn.nextInt();
        }

        int size2 = scn.nextInt();
        int[] arr2 = new int[size2];
        for (int i = 0; i < arr2.length; i++) {
            arr2[i] = scn.nextInt();
        }
        addTwoArray(arr1 , arr2);
    }

    public static void addTwoArray(int[] arr1 , int[] arr2) {

        int n1 = arr1.length;
        int n2 = arr2.length;
        int sizeAns = (n1 > n2) ? n1 + 1 : n2 + 1;
        int[] ans = new int[sizeAns];
        int i = n1 - 1;
        int j = n2 - 1;
        int k = ans.length - 1;

        int carry = 0;
        while (i >= 0 || j >= 0) {
            int sum = carry;
            if (i >= 0) {
                sum += arr1[i];
            }
            if (j >= 0) {
                sum += arr2[j];
            }
            carry = sum / 10;
            sum = sum % 10;

            ans[k] = sum;
            i--; j--; k--;
        }
        if (carry > 0) {
            ans[k] = carry;
        }

        for (i =0; i < ans.length; i++) {
            int val = ans[i];
            if (i == 0 && val > 0) {
                System.out.println(val);
            }
            else if (i > 0) {
                System.out.println(val);
            }
        }

    }

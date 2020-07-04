# DailyInterviewPro-solutions
Answers to daily interview pro questions 
 public class InterviewQuestions{
    
    /**
     * sum of digits of num
     * @param num
     */
    public int sumOfNum(int num){
        int sum = 0;
        while (num != 0){
           int digit = num%10;
           sum = sum + digit;
           num = num/10;
        }
       return sum;
    }

    /**
     * sum until num becomes single digit ex: 167
     * 1+6+7 = 14
     * 1+4 = 5
     * @param num
     */
    public void sumRoundToSingleDigitNo(int num){
       int sum = sumOfNum(num);
       if(sum < 10){
           System.out.println(sum);
       } else {
           sumRoundToSingleDigitNo(sumOfNum(sum));
       }
    }

    /**
     * do division without using symbols,
     * adding number for the given times gives multiplication , same subtracting numerator with denominator gives division result
     * @param  - numerator
     * @param - denominator
     */
    public int division(int numerator, int denominator){
        int reminder = numerator;
        int result = 0;
        while((reminder-denominator) > 0) {
            numerator = numerator - denominator;
            result++;
            reminder = numerator;
        }
        return result;
    }

    public int modulus(int numerator, int denominator) {
        int reminder = numerator;
        int result = 0;
        while ((reminder - denominator) > 0) {
            numerator = numerator - denominator;
            result++;
            reminder = numerator;
        }
        return reminder;
    }
   public void duplicateElements(int[] array){
        int[] duplicateArray = new int[totalDuplicateElements(array)];
        int index = 0;
        for(int j = 0; j < array.length; j++) {
            int count = 0;
            for (int i = 0; i < array.length; i++) {
                if (array[j] == array[i]) {
                    count++;
                }
            }
            if(count > 1){
                duplicateArray[index] = array[j];
                index++;
                array[j] = 0;// in order to avoid printing twice making element at that particular index 0
            }
        }
        // this loop is to print elements 
        for(int j = 0; j < duplicateArray.length; j++){
            System.out.println(duplicateArray[j]);
        }
    }

 public int totalDuplicateElements(int[] array) {
        int duplicates = 0;
        for (int j = 0; j < array.length; j++) {
            int count = 0;
            for (int i = 0; i < array.length; i++) {
                if (array[j] == array[i]) {
                    count++;
                }
            }
            if (count > 1) {
                duplicates++;
            }
        }
        return duplicates - (duplicates/2);
    }
}

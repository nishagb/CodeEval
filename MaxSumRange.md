import java.io.*;
import java.util.*;
public class Main {
    public static void main (String[] args) throws IOException {
        File file = new File(args[0]);
        BufferedReader buffer = new BufferedReader(new FileReader(file));
        String line;
        while ((line = buffer.readLine()) != null) {
            line = line.trim();
            
            
            
            	//	String givenArray="5;7 -3 -10 4 2 8 -2 4 -5 -2";
		String[] n1=line.split(";");
		
		int n=Integer.parseInt(n1[0]);
	//	System.out.println(n);
		int line1[] = new int[100];
		int numOfTokens = 0;
		
		
		 StringTokenizer tokenizer = new StringTokenizer(line, " ");

         while (tokenizer.hasMoreTokens()) {

             String digits = tokenizer.nextToken();

              if (digits.contains(";")) {
            	 String digitArray[]=digits.split(";");
            	 int lhs=Integer.parseInt(digitArray[0]);
            	 if(lhs>9)
            	 {
            	 digits=digitArray[1];
            	 }
            	 else{
                 digits = (digits.substring(2));
            	 	}
            }

             line1[numOfTokens] = Integer.parseInt(digits);
//System.out.println(line1[numOfTokens]);
numOfTokens++;
         }
         
         //System.out.println("line1 length is "+line1.length);
        // System.out.println("i is "+numOfTokens);
         int firstIndex,lastIndex,sum=0,finalSum=0,finalFirstIndex = 0,finalLastIndex = 0;
 		for (int i1 = 0; i1 < numOfTokens; i1++) {
 			firstIndex=i1;lastIndex=firstIndex+n;sum=0;
 			if(lastIndex<=numOfTokens)
 			{
 			for (int j = firstIndex; j < lastIndex; j++) {
 				sum=sum+line1[j];
 				
 				}
 			}
 			//finalSum=sum;
 			//System.out.println("sum is "+sum);
 			//sum=sum+subArray[firstIndex];
 			if(sum>finalSum)
 			{
 				finalSum=sum;
 				finalFirstIndex=firstIndex;
 				finalLastIndex=lastIndex;
 			}
 		}
 			System.out.println(finalSum);
 			
        }
    }
}

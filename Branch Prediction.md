##分支预测与有序：
  
      public class BranchPredictionTest {
	
        public static void main(String[] args) {
          // Generate data
          int arraySize = 32768;
          int data[] = new int[arraySize];

          Random rnd = new Random(0);
          for (int c = 0; c < arraySize; ++c)
            data[c] = rnd.nextInt() % 256;

          // Test no sorted
          long start = System.nanoTime();
          long sum = 0;

          for (int i = 0; i < 100000; ++i)
          {
            // Primary loop 
            for (int c = 0; c < arraySize; ++c)
            {
              if (data[c] >= 128)
                sum += data[c];
            }
          }

          System.out.println("no sorted time : " +(System.nanoTime() - start) / 1000000000.0);
          System.out.println("sum = " + sum);
          // !!! With this, the next loop runs faster
          Arrays.sort(data);

          long startSort = System.nanoTime();
          long sumSort = 0;

          for (int i = 0; i < 100000; ++i)
          {
            // Primary loop
            for (int c = 0; c < arraySize; ++c)
            {
              if (data[c] >= 128)
                sumSort += data[c];
            }
          }

          System.out.println("sorted time : " + (System.nanoTime() - startSort) / 1000000000.0);
          System.out.println("sumSort = " + sumSort);

        }
      }
      
      ![结果对比](https://github.com/FRookie/My-Grocery-Store/blob/master/picture/differ.PNG)

# offer14-cut-pipe
剑指offer14题--剪绳子我的独到见解
### 这道题的常规思想是动态规划和贪婪算法，但在常规思想的同时我们一定要寻找解题的真解，转变思想，才能突破！
### 废话不多说，先上代码

public int cuttingRope(int n) {
//剪绳子问题 算数法

        if(n<=3){
            return n-1;
        }else if(n==4){//重点 2*2是要比1*3大的
            return 4;
        }else{
            int a = n/3;
            int b = n%3;
            int sum = 1;
            if(b==1){
                a = a-1;//与n=4时单独提出来是一个道理
                for(int i=0;i<a;i++){
                    sum = sum * 3;
                }
                sum = sum * 4;
            }else if(b == 0){
                for(int i=0;i<a;i++){
                    sum = sum * 3;
                }
            }else if(b == 2){
                for(int i=0;i<a;i++){
                    sum = sum * 3;
                }
                sum = sum * 2;
            }
            return sum;
        }

    }
#### 任何数字都可转换为2与3相加，而由其转换为的相乘才会得到最大值，具体原因自己求导。
#### 注意当取余是1 时要将1与除后的一个3合并为4，将其与剩余的3相乘才为最大！

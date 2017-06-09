
The main method is in this program itself.

Instructions for compiling=>>
my IDE codeBlocks;

Run on any gcc compiler=>>

Special***** should compile in -std=c++11 or c++14 *********  (mat be other versions syntacs can be different)

turorials point online compiler
==> go to link  http://cpp.sh/ or  https://www.tutorialspoint.com/compile_cpp_online.php  and after go to c++ editor copy code and paste.
after that click button compile and after execute. 

if you have -std=c++11 or C++14 you can run in command line;
g++ -o output Simplex.cpp
./output

if you correctly compile this Output should like this:
Output:
		
	initial array(Not optimal)
	2 1 1 1 0 0 
	1 3 2 0 1 0 
	2 1 2 0 0 1 

	 
	final array(Optimal solution)
	1 0 0.2 0.6 -0.2 0 
	0 1 0.6 -0.2 0.4 0 
	0 0 1 -1 0 1 

	Answers for the Constraints of variables(variables array)
	variable1: 48
	variable2: 84
	variable3: 0

	maximum value: 708



How to give inputs to the program =>>>

   Example qution:    maximize -->  6x + 5y + 4z

		      Subject to  2x + y + z <= 180    slack varibles  2x + y + z + s1 = 180  
				  x + 3y + 2z <= 300                   x + 3y + 2z +s2 = 300
				  2x + y + 2z <= 240                    2x + y + 2z +s3 = 240

  you can make a arryas like below from this quetion:
        colSizeA = 6 // input colmn size
	rowSizeA = 3  // input row size
    float C[N]={-6,-5,-4,0,0,0};  //Initialize the C array  with the coefficients of the constraints of the objective function
    float B[M]={180,300,240};//Initialize the B array constants of the constraints respectively


   //initialize the A array by giving all the coefficients of all the variables
   float A[M][N] =  {
                 { 2,  1,  1,   1,  0, 0},
                { 1,  3,  2,   0,  1, 0 },
                {   2,    1,  2,   0,  0,  1}
                };

after intialis these arrays make the Simplex class and call CalculateSimplex() method:
                                               
                     Simplex simplex(vec2D,b,c);
                     simplex.CalculateSimplex();

NumPy[¶](#NumPy) {#NumPy}
================

Python package used for working with arrays ,linear algebra ,fourier
transform and matrices.

Includes special mathematical functions like cosine ,exponent , square
root etc

Faster than traditional python lists as NP arrays are stored at one
continuous place in memory.

To use numPy , it has to be imported using the keyword 'import'

In [2]:

    # alias numpy as np

    import numpy as np

Different methods to create an array / matrices using numpy

In [3]:

    # Simple method 
    # converting list into a np array 1D

    arr = np.array([1,2,3,4,5,6,7,8])
    print('')
    print(arr)

    [1 2 3 4 5 6 7 8]

In [4]:

    # Using arange function to generate an array

    arr1 = np.arange(10)
    print('')
    print(arr1)

    [0 1 2 3 4 5 6 7 8 9]

In [5]:

    # arange function also takes two arg start and end where start is inclusive and stop is exclusive

    arr2 = np.arange(2,10)
    print('')
    print(arr2)
    print("Array includes start element 2 whereas excludes 10 ")

    [2 3 4 5 6 7 8 9]
    Array includes start element 2 whereas excludes 10 

In [6]:

    # arange func with three arg

    arr3 = np.arange(1,10,2)                     # third arg specifies the spacing or difference bet consecutive values
    print('')
    print(arr3)

    [1 3 5 7 9]

In [7]:

    # linspace is one more arraty creation function

    arr4 = np.linspace(2,20, num = 10)           # num tell number of values to be generated  
    print('')
    print(arr4)

    [ 2.  4.  6.  8. 10. 12. 14. 16. 18. 20.]

In [8]:

    # 3 * 3 array creation using np array

    arr5 = np.array([[1,2,3],[2,3,4],[3,5,4]])
    print('')
    print(arr5)

    [[1 2 3]
     [2 3 4]
     [3 5 4]]

In [9]:

    # array creation 2D / ND

    # create a matrix with all zero entries using zeros function
     
    mat1 = np.zeros([3,3])                  
    print('')
    print(mat1)

    [[0. 0. 0.]
     [0. 0. 0.]
     [0. 0. 0.]]

In [10]:

    # create a 4 * 4 matix with all entries 1 using ones function

    mat2 = np.ones([4,4])
    print('')
    print(mat2)

    [[1. 1. 1. 1.]
     [1. 1. 1. 1.]
     [1. 1. 1. 1.]
     [1. 1. 1. 1.]]

In [11]:

    # create an identity matrix using eye function

    mat3 = np.eye(4)
    print('')
    print(mat3)

    [[1. 0. 0. 0.]
     [0. 1. 0. 0.]
     [0. 0. 1. 0.]
     [0. 0. 0. 1.]]

In [12]:

    # create a 4 * 3 matrix

    mat4  = np.matrix([[1,2,3],[4,5,6],[6,7,8],[8,9,0]])     
    print('')
    print(mat4)

    [[1 2 3]
     [4 5 6]
     [6 7 8]
     [8 9 0]]

In [13]:

     # create a constant array with value 6 using full function

    mat5 = np.full((3 ,3 ), 6)          
    print('')
    print(mat5)

    [[6 6 6]
     [6 6 6]
     [6 6 6]]

Array sample creation using random variable Three variants 1: simple
random data returns sample from uniform distribution over (0 , 1) 2:
standard normal data Returns sample from standard normal distribution 3:
Random integers returns random integers from low to high

In [14]:

    # Simple random data generation

    arr6 = np.random.rand(5,5)
    print('')
    print(arr6)

    [[1.19223667e-01 8.78951566e-01 3.98095927e-06 3.60120177e-01
      7.45155250e-02]
     [4.19922688e-01 3.16441563e-01 9.33642695e-01 1.92267494e-01
      7.97280196e-02]
     [9.68530212e-01 3.21748276e-01 3.66132810e-01 1.47865754e-01
      9.29486250e-01]
     [4.21145732e-01 8.28107144e-01 9.75452727e-01 1.78361408e-01
      3.27671108e-02]
     [9.76909182e-01 2.29477008e-01 9.75578046e-01 7.95896153e-01
      6.84023990e-01]]

In [15]:

    # standard normal

    arr7 = np.random.randn(2,4)
    print('')
    print(arr7)

    [[-0.25320376 -0.53735953 -1.72060809  0.35703393]
     [ 0.59221671  0.79733818 -0.01820985 -0.76274819]]

In [16]:

    # random integers

    arr8 = np.random.randint(50, size=(2,3))
    print('')
    print(arr8)

    [[ 5 26 32]
     [ 2 21  2]]

Array Indexing

1 : Slicing Numpy arrays can be sliced similar to python list but one
thing to note here is since numpy array is N dimensional , required to
specify slice for each dimension

In [17]:

    import numpy as np

    # create an array of the shape [3,4]
    # [1 , 2, 4, 5]
    # [2, 3, 5, 6]
    # [3, 4, 5, 6]

    arr6 = np.matrix([[1, 2, 4, 5] ,[2, 3, 5, 6] ,[3, 4, 5, 6]])
    print('')
    print(arr6)

    # use slicing to obtain the sub array of 2 * 2 with first two rows
    # consisting column 2 and 3 

    arr7 = arr6[0:2,1:3]                            
    print('')
    print("sub array of arr6 is:")
    print('')
    print(arr7)

    [[1 2 4 5]
     [2 3 5 6]
     [3 4 5 6]]

    sub array of arr6 is:

    [[2 4]
     [3 5]]

2 : Boolean Array Indexing Allows to pull the elements which satisfies
the condition provided

In [18]:

    # create an array and pick all the even numbers 

    arr8 = np.matrix([[1, 2, 3, 4] ,[2, 4, 6, 8] ,[4, 6, 8, 1] ])

    bool_arr = (arr8 % 2 == 0)             # Checks for the even numbers in an array and returns numpy boolean array 
                                           # with same shape as the original array  , each element tells whether 
                                           # the number is even or not


    print('Boolean Array is\n')
    print(bool_arr)                        # prints boolean array
                                           # [[False  True False  True]
                                           #  [ True  True  True  True]
                                           #  [ True  True  True False]]

    print('')

    print(arr8[bool_arr])                 # prints all the even numbers [[2 4 2 4 6 8 4 6 8]]

    Boolean Array is

    [[False  True False  True]
     [ True  True  True  True]
     [ True  True  True False]]

    [[2 4 2 4 6 8 4 6 8]]

3 : Integer Array Indexing Slicing gives the subarray of the original
array whereas integer indexing allows us to construct arbitrary array
using the elements from another array.

In [19]:

    # create an array 

    arr9 = np.matrix([[1, 2] ,[3, 4]])

    print('\n original array \n')
    print(arr9)                                         # prints  [[1 2]
                                                        #           [3 4]]


    intindex_arr = arr9[[0, 1],[0 ,1]]                  # selects 0 row 0 colum element which is 1 and 1:1 element
                                                        # which is 4

    print('\n Arbitrary array created using original \n')

    print(intindex_arr)                                 # prints [[1 4]]

     original array 

    [[1 2]
     [3 4]]

     Arbitrary array created using original 

    [[1 4]]

In [23]:

    # Unique fuction to extract unique element from the array

    arr10 = np.array([[1, 1,  1],[1, 4, 4]])
    print(" ")
    print(arr10)
    print(' ')
    print(np.unique(arr10))

     
    [[1 1 1]
     [1 4 4]]
     
    [1 4]

In [26]:

    # shape function to get the shape of an array

    arr11 = np.random.rand(4 ,5)                       # prints 4 * 5 array of random elements 
    print(' ')
    print(arr11)
    print(' ')
    print(np.shape(arr11))                             # returns (4, 5) which is the shape of the array

     
    [[0.82481198 0.35889045 0.33064443 0.64380939 0.87625921]
     [0.69431954 0.31832415 0.26573783 0.52101688 0.26291467]
     [0.42439501 0.01412467 0.25213884 0.09869507 0.54354276]
     [0.50928079 0.71950532 0.05103175 0.3933701  0.71877822]]
     
    (4, 5)

In [27]:

    # dimension of an array

    arr12 = np.random.rand(3 ,4)
    print(' ')
    print(np.ndim(arr12))                               # returns dimension of the array i.e 2

     
    2

DataTypes

Numpy array is made of elements of same type .It provides a set of large
numeric data type . It finds the data type during the creation of an
array. Can also specify datatype explicitly in the funtions argument.

In [28]:

    # create an array and find its data type

    arr13 = np.random.rand(3 ,4)
    print(' ') 
    print(arr13.dtype)                                  # returns the datatype of the array

     
    float64

In [31]:

    #create a random array and explicitly specify its data type 

    arr14 = np.array([3 , 3] , dtype = np.int64)
    print(' ') 
    print(arr14.dtype)                                  # returns the datatype of the array

     
    int64

In [ ]:

     

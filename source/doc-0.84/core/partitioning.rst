Matrix partitions
=================
The following routines are slight tweaks of the FLAME project's 
(as well as PLAPACK's) approach to submatrix tracking; the difference is that 
they have "locked" versions, which are meant for creating partitionings where 
the submatrices cannot be modified.

PartitionUp
-----------
Given an :math:`m \times n` matrix `A`, configure `AT` and `AB` to view the local data of `A` corresponding to the partition

.. math::

   A = \left(\begin{array}{c}A_T \\ A_B \end{array}\right), 

where :math:`A_B` is of a specified height. 

.. cpp:function:: void PartitionUp( Matrix<T>& A, Matrix<T>& AT, Matrix<T>& AB, int heightAB=Blocksize() )
.. cpp:function:: void LockedPartitionUp( const Matrix<T>& A, Matrix<T>& AT, Matrix<T>& AB, int heightAB=Blocksize() )

   Templated over the datatype, `T`, of the serial matrix `A`.

.. cpp:function:: void PartitionUp( DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& AT, DistMatrix<T,U,V>& AB, int heightAB=Blocksize() )
.. cpp:function:: void LockedPartitionUp( const DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& AT, DistMatrix<T,U,V>& AB, int heightAB=Blocksize() )

   Templated over the datatype, `T`, and distribution scheme, `(U,V)`, 
   of the distributed matrix `A`.


PartitionDown
-------------
Given an :math:`m \times n` matrix `A`, configure `AT` and `AB` to view the local data of `A` corresponding to the partition

.. math::

   A = \left(\begin{array}{c}A_T \\ A_B \end{array}\right),

where :math:`A_T` is of a specified height.

.. cpp:function:: void PartitionDown( Matrix<T>& A, Matrix<T>& AT, Matrix<T>& AB, int heightAT=Blocksize() )
.. cpp:function:: void LockedPartitionDown( const Matrix<T>& A, Matrix<T>& AT, Matrix<T>& AB, int heightAT=Blocksize() )

   Templated over the datatype, `T`, of the serial matrix `A`.

.. cpp:function:: void PartitionDown( DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& AT, DistMatrix<T,U,V>& AB, int heightAT=Blocksize() )
.. cpp:function:: void LockedPartitionDown( const DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& AT, DistMatrix<T,U,V>& AB, int heightAT=Blocksize() )

   Templated over the datatype, `T`, and distribution scheme, `(U,V)`, 
   of the distributed matrix `A`.

PartitionLeft
-------------
Given an :math:`m \times n` matrix `A`, configure `AL` and `AR` to view the local data of `A` corresponding to the partition

.. math::

   A = \left(\begin{array}{cc} A_L & A_R \end{array}\right),

where :math:`A_R` is of a specified width.

.. cpp:function:: void PartitionLeft( Matrix<T>& A, Matrix<T>& AL, Matrix<T>& AR, int widthAR=Blocksize() )
.. cpp:function:: void LockedPartitionLeft( const Matrix<T>& A, Matrix<T>& AL, Matrix<T>& AR, int widthAR=Blocksize() )

   Templated over the datatype, `T`, of the serial matrix `A`.

.. cpp:function:: void PartitionLeft( DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& AL, DistMatrix<T,U,V>& AR, int widthAR=Blocksize() )
.. cpp:function:: void LockedPartitionLeft( const DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& AL, DistMatrix<T,U,V>& AR, int widthAR=Blocksize() )

   Templated over the datatype, `T`, and the distribution scheme, `(U,V)`, 
   of the distributed matrix `A`.

PartitionRight
--------------
Given an :math:`m \times n` matrix `A`, configure `AL` and `AR` to view the local data of `A` corresponding to the partition

.. math::

   A = \left(\begin{array}{cc} A_L & A_R \end{array}\right),

where :math:`A_L` is of a specified width.

.. cpp:function:: void PartitionRight( Matrix<T>& A, Matrix<T>& AL, Matrix<T>& AR, int widthAL=Blocksize() )
.. cpp:function:: void LockedPartitionRight( const Matrix<T>& A, Matrix<T>& AL, Matrix<T>& AR, int widthAL=Blocksize() )

   Templated over the datatype, `T`, of the serial matrix `A`.

.. cpp:function:: void PartitionRight( DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& AL, DistMatrix<T,U,V>& AR, int widthAL=Blocksize() )
.. cpp:function:: void LockedPartitionRight( const DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& AL, DistMatrix<T,U,V>& AR, int widthAL=Blocksize() )

   Templated over the datatype, `T`, and the distribution scheme, `(U,V)`, 
   of the distributed matrix `A`.

PartitionUpDiagonal
-------------------
Given an :math:`m \times n` matrix `A`, configure `ATL`, `ATR`, `ABL`, and `ABR` to view the local data of `A` corresponding to the partitioning

.. math::

   A = \left(\begin{array}{cc} A_{TL} & A_{TR} \\ A_{BL} & A_{BR} \end{array}\right),

where the diagonal of :math:`A_{BR}` lies on the main diagonal 
(aka, the *left* diagonal) of :math:`A` and is of the specified height/width.

.. cpp:function:: void PartitionUpDiagonal( Matrix<T>& A, Matrix<T>& ATL, Matrix<T>& ATR, Matrix<T>& ABL, Matrix<T>& ABR, int diagDist=Blocksize() )
.. cpp:function:: void LockedPartitionUpDiagonal( const Matrix<T>& A, Matrix<T>& ATL, Matrix<T>& ATR, Matrix<T>& ABL, Matrix<T>& ABR, int diagDist=Blocksize() )

   Templated over the datatype, `T`, of the serial matrix `A`.

.. cpp:function:: void PartitionUpDiagonal( DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& ATL, DistMatrix<T,U,V>& ATR, DistMatrix<T,U,V>& ABL, DistMatrix<T,U,V>& ABR, int diagDist=Blocksize() )
.. cpp:function:: void LockedPartitionUpDiagonal( const DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& ATL, DistMatrix<T,U,V>& ATR, DistMatrix<T,U,V>& ABL, DistMatrix<T,U,V>& ABR, int diagDist=Blocksize() )

   Templated over the datatype, `T`, and the distribution scheme, `(U,V)`,
   of the distributed matrix `A`.

PartitionUpOffsetDiagonal
-------------------------
Given an :math:`m \times n` matrix `A`, configure `ATL`, `ATR`, `ABL`, and `ABR` to view the local data of `A` corresponding to the partitioning

.. math::

   A = \left(\begin{array}{cc} A_{TL} & A_{TR} \\ A_{BL} & A_{BR} \end{array}\right),

where the diagonal of :math:`A_{BR}` lies on the ``offset`` diagonal of 
:math:`A`, where the main diagonal corresponds to an offset of 0, the 
subdiagonal is an offset of :math:`-1`, the superdiagonal is an offset of 
:math:`1`, etc. The length of the diagonal of :math:`A_{BR}` is specified as
``diagDist``.

.. cpp:function:: void PartitionUpOffsetDiagonal( int offset, Matrix<T>& A, Matrix<T>& ATL, Matrix<T>& ATR, Matrix<T>& ABL, Matrix<T>& ABR, int diagDist=Blocksize() )
.. cpp:function:: void LockedPartitionUpOffsetDiagonal( int offset, const Matrix<T>& A, Matrix<T>& ATL, Matrix<T>& ATR, Matrix<T>& ABL, Matrix<T>& ABR, int diagDist=Blocksize() )

   Templated over the datatype, `T`, of the serial matrix `A`.

.. cpp:function:: void PartitionUpOffsetDiagonal( int offset, DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& ATL, DistMatrix<T,U,V>& ATR, DistMatrix<T,U,V>& ABL, DistMatrix<T,U,V>& ABR, int diagDist=Blocksize() )
.. cpp:function:: void LockedPartitionUpOffsetDiagonal( int offset, const DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& ATL, DistMatrix<T,U,V>& ATR, DistMatrix<T,U,V>& ABL, DistMatrix<T,U,V>& ABR, int diagDist=Blocksize() )

   Templated over the datatype, `T`, and the distribution scheme, `(U,V)`,
   of the distributed matrix `A`.

PartitionDownDiagonal
---------------------
Given an :math:`m \times n` matrix `A`, configure `ATL`, `ATR`, `ABL`, and `ABR` to view the local data of :math:`A` corresponding to the partitioning

.. math::

   A = \left(\begin{array}{cc} A_{TL} & A_{TR} \\ A_{BL} & A_{BR} \end{array}\right),

where the diagonal of :math:`A_{TL}` is of the specified length and lies on 
the main diagonal (aka, the *left* diagonal) of :math:`A`. 

.. cpp:function:: void PartitionDownDiagonal( Matrix<T>& A, Matrix<T>& ATL, Matrix<T>& ATR, Matrix<T>& ABL, Matrix<T>& ABR, int diagDist=Blocksize() )
.. cpp:function:: void LockedPartitionDownDiagonal( const Matrix<T>& A, Matrix<T>& ATL, Matrix<T>& ATR, Matrix<T>& ABL, Matrix<T>& ABR, int diagDist=Blocksize() )

   Templated over the datatype, `T`, of the serial matrix `A`.

.. cpp:function:: void PartitionDownDiagonal( DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& ATL, DistMatrix<T,U,V>& ATR, DistMatrix<T,U,V>& ABL, DistMatrix<T,U,V>& ATL, int diagDist=Blocksize() )
.. cpp:function:: void LockedPartitionDownDiagonal( const DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& ATL, DistMatrix<T,U,V>& ATR, DistMatrix<T,U,V>& ABL, DistMatrix<T,U,V>& ABR, int diagDist=Blocksize() )

   Templated over the datatype, `T`, and the distribution scheme, `(U,V)`,
   of the distributed matrix `A`.
 
PartitionDownOffsetDiagonal
---------------------------
Given an :math:`m \times n` matrix `A`, configure `ATL`, `ATR`, `ABL`, and `ABR` to view the local data of `A` corresponding to the partitioning

.. math::

   A = \left(\begin{array}{cc} A_{TL} & A_{TR} \\ A_{BL} & A_{BR} \end{array}\right),

where the diagonal of :math:`A_{BR}` lies on the ``offset`` diagonal of 
:math:`A`, where the main diagonal corresponds to an offset of 0, the 
subdiagonal is an offset of :math:`-1`, the superdiagonal is an offset of 
:math:`1`, etc. The length of the diagonal of :math:`A_{TL}` is specified as
``diagDist``.

.. cpp:function:: void PartitionDownOffsetDiagonal( int offset, Matrix<T>& A, Matrix<T>& ATL, Matrix<T>& ATR, Matrix<T>& ABL, Matrix<T>& ABR, int diagDist=Blocksize() )
.. cpp:function:: void LockedPartitionDownOffsetDiagonal( int offset, const Matrix<T>& A, Matrix<T>& ATL, Matrix<T>& ATR, Matrix<T>& ABL, Matrix<T>& ABR, int diagDist=Blocksize() )

   Templated over the datatype, `T`, of the serial matrix `A`.

.. cpp:function:: void PartitionDownOffsetDiagonal( int offset, DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& ATL, DistMatrix<T,U,V>& ATR, DistMatrix<T,U,V>& ABL, DistMatrix<T,U,V>& ATL, int diagDist=Blocksize() )
.. cpp:function:: void LockedPartitionDownOffsetDiagonal( int offset, const DistMatrix<T,U,V>& A, DistMatrix<T,U,V>& ATL, DistMatrix<T,U,V>& ATR, DistMatrix<T,U,V>& ABL, DistMatrix<T,U,V>& ABR, int diagDist=Blocksize() )

   Templated over the datatype, `T`, and the distribution scheme, `(U,V)`,
   of the distributed matrix `A`.

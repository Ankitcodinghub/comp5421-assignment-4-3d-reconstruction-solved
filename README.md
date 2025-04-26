# comp5421-assignment-4-3d-reconstruction-solved
**TO GET THIS SOLUTION VISIT:** [COMP5421 Assignment 4-3D Reconstruction Solved](https://www.ankitcodinghub.com/product/comp5421-homework-assignment-4-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;124261&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;COMP5421 Assignment 4-3D Reconstruction Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
3D Reconstruction

Make sure to start early!

Part I: Theory

Q1.1 (5 points) Suppose two cameras fixate on a point P (see Figure 1) in space such that their principal axes intersect at that point. Show that if the image coordinates are normalized so that the coordinate origin (0,0) coincides with the principal point, the F33 element of the fundamental matrix is zero.

Figure 1: Figure for Q1.1. C1 and C2 are the optical centers. The principal axes intersect at point P.

Q1.2 (5 points) Consider the case of two cameras viewing an object such that the second camera differs from the first by a pure translation that is parallel to the x-axis. Show that the epipolar lines in the two cameras are also parallel to the x-axis. Backup your argument with relevant equations.

Q1.3 (5 points) Suppose we have an inertial sensor which gives us the accurate positions (Ri and ti, where R is the rotation matrix and t is corresponding translation vector) of the robot at time i. What will be the effective rotation (Rrel ) and translation (trel ) between two frames at different time stamps? Suppose the camera intrinsics (K) are known, express the essential matrix (E) and the fundamental matrix (F) in terms of K, Rrel and trel.

Q1.4 (10 points) Suppose that a camera views an object and its reflection in a plane mirror.

Figure 2: Figure for Q1.3. C1 and C2 are the optical centers. The rotation and the translation is obtained using inertial sensors. Rrel and trel are the relative rotation and translation between two frames.

Part II: Practice

1 Overview

In this part you will begin by implementing the two different methods seen in class to estimate the fundamental matrix from corresponding points in two images (Section 2). Next, given the fundamental matrix and calibrated intrinsics (which will be provided) you will compute the essential matrix and use this to compute a 3D metric reconstruction from 2D correspondences using triangulation (Section 3). Then, you will implement a method to automatically match points taking advantage of epipolar constraints and make a 3D visualization of the results (Section 4). Finally, you will implement RANSAC and bundle adjustment to further improve your algorithm (Section

5).

2 Fundamental matrix estimation

In this section you will explore different methods of estimating the fundamental matrix given a pair of images. In the data/ directory, you will find two images (see Figure 3) from the Middlebury multiview dataset , which is used to evaluate the performance of modern 3D reconstruction algorithms.

The Eight Point Algorithm

The 8-point algorithm (discussed in class, and outlined in Section 10.1 of Forsyth &amp; Ponce) is arguably the simplest method for estimating the fundamental matrix. For this section, you can use

Figure 3: Temple images for this assignment

Figure 4: displayEpipolarF in helper.py creates a GUI for visualizing epipolar lines

provided correspondences you can find in data/some corresp.npz.

Q2.1 (10 points) Finish the function eightpoint in submission.py. Make sure you follow the signature for this portion of the assignment:

F = eightpoint(pts1, pts2, M)

where pts1 and pts2 are N × 2 matrices corresponding to the (x,y) coordinates of the N points in the first and second image repectively. M is a scale parameter.

• You should scale the data as was discussed in class, by dividing each coordinate by M (the maximum of the image’s width and height). After computing F, you will have to “unscale” the fundamental matrix.

Hint: If xnormalized = Tx, then Funnormalized = TTFT.

You must enforce the singularity condition of the F before unscaling.

For this we have provided a helper function refineF in helper.py taking in F and the two sets of points, which you can call from eightpoint before unscaling F.

• Remember that the x-coordinate of a point in the image is its column entry, and y-coordinate is the row entry. Also note that eight-point is just a figurative name, it just means that you need at least 8 points; your algorithm should use an over-determined system (N &gt; 8 points).

• To visualize the correctness of your estimated F, use the supplied function displayEpipolarF in helper.py, which takes in F, and the two images. This GUI lets you select a point in one of the images and visualize the corresponding epipolar line in the other image (Figure 4).

• Output: Save your matrix F, scale M to the file q2 1.npz.

In your write-up: Write your recovered F and include an image of some example output of displayEpipolarF.

The Seven Point Algorithm

Q2.2 (15 points) Since the fundamental matrix only has seven degrees of freedom, it is possible to calculate F using only seven point correspondences. This requires solving a polynomial equation. In the section, you will implement the seven-point algorithm (described in class, and outlined in Section 15.6 of Forsyth and Ponce). Manually select 7 points from provided point in data/some corresp.npz, and use these points to recover a fundamental matrix F. The function should have the signature:

Farray = sevenpoint(pts1, pts2, M)

where pts1 and pts2 are 7 × 2 matrices containing the correspondences and M is the normalizer (use the maximum of the images’ height and width), and Farray is a list array of length either 1 or 3 containing Fundamental matrix/matrices. Use M to normalize the point values between [0,1] and remember to “unnormalize” your computed F afterwards.

• Use displayEpipolarF to visualize F and pick the correct one.

• Output: Save your matrix F, scale M, 2D points pts1 and pts2 to the file q2 2.npz.

In your write-up: Write your recovered F and print an output of displayEpipolarF. Also, include an image of some example output of displayEpipolarF using the seven point algorithm.

3 Metric Reconstruction

Q3.1 (5 points) Write a function to compute the essential matrix E given F,K1 and K2 with the signature

E = essentialMatrix(F, K1, K2)

In your write-up: Write your estimated E using F from the eight-point algorithm. Given an essential matrix, it is possible to retrieve the projective camera matrices M1 and M2 from it. Assuming M1 is fixed at [I,0], M2 can be retrieved up to a scale and four-fold rotation ambiguity. For details on recovering M2 , see section 7.2 in Szeliski. We have provided you with the function camera2 in python/helper.py to recover the four possible M2 matrices given E.

Note: The M1 and M2 here are projection matrices of the form: M1 = [I|0] and M2 = [R|t].

Q3.2 (10 points) Using the above, write a function to triangulate a set of 2D coordinates in the image to a set of 3D points with the signature:

[P, err] = triangulate(C1, pts1, C2, pts2)

where pts1 and pts2 are the N×2 matrices with the 2D image coordinates and P is an N×3 matrix with the corresponding 3D points per row. C1 and C2 are the 3×4 camera matrices. Remember that you will need to multiply the given intrinsics matrices with your solution for the canonical camera matrices to obtain the final camera matrices. Various methods exist for triangulation probably the most familiar for you is based on least squares (see Szeliski Chapter 7 if you want to learn about other methods).

For each point i, we want to solve for 3D coordinates Pi = [xi,yi,zi]T , such that when they are projected back to the two images, they are close to the original 2D points. To project the 3D coordinates back to 2D images, we first write Pi in homogeneous coordinates, and compute C1Pi and C2Pi to obtain the 2D homogeneous coordinates projected to camera 1 and camera 2, respectively.

For each point i, we can write this problem in the following form:

AiPi = 0,

where Ai is a 4×4 matrix, and Pi is a 4×1 vector of the 3D coordinates in the homogeneous form. Then, you can obtain the homogeneous least-squares solution (discussed in class) to solve for each

Pi.

In your write-up: Write down the expression for the matrix Ai.

Once you have implemented triangulation, check the performance by looking at the reprojection error:

err = Xkp1i,pˆ1ik2 + kp2i,pˆ2ik2

i

where ˆp1i = Proj(C1,Pi) and ˆp2i = Proj(C2,Pi).

Note: C1 and C2 here are projection matrices of the form: C1 = K1M1 = K1[I|0] and C2 = K2M2 = K2[R|t].

Q3.3 (10 points) Write a script findM2.py to obtain the correct M2 from M2s by testing the four solutions through triangulations. Use the correspondences from data/somecorresp.npz. Output: Save the correct M2, the corresponding C2, and 3D points P to q3 3.npz.

4 3D Visualization

You will now create a 3D visualization of the temple images. By treating our two images as a stereo-pair, we can triangulate corresponding points in each image, and render their 3D locations.

Q4.1 (15 points) Implement a function with the signature:

[x2, y2] = epipolarCorrespondence(im1, im2, F, x1, y1)

This function takes in the x and y coordinates of a pixel on im1 and your fundamental matrix F, and returns the coordinates of the pixel on im2 which correspond to the input point. The match is obtained by computing the similarity of a small window around the (x1,y1) coordinates in im1 to various windows around possible matches in the im2 and returning the closest.

Instead of searching for the matching point at every possible location in im2, we can use F and simply search over the set of pixels that lie along the epipolar line (recall that the epipolar line passes through a single point in im2 which corresponds to the point (x1,y1) in im1.

There are various possible ways to compute the window similarity. For this assignment, simple methods such as the Euclidean or Manhattan distances between the intensity of the pixels should suffice. See Szeliski Chapter 11, on stereo matching, for a brief overview of these and other methods. Implementation hints:

• Experiment with various window sizes.

• Since the two images only differ by a small amount, it might be beneficial to consider matches for which the distance from (x1,y1) to (x2,y2) is small.

To test your epipolarCorrespondence, we have included a helper function epipolarMatchGUI in python/helper.py, which takes in two images the fundamental matrix. This GUI allows you to click on a point in im1, and will use your function to display the corresponding point in im2. See Figure 5.

It is not necessary for your matcher to get every possible point right, but it should get easy points (such as those with distinctive, corner-like windows). It should also be good enough to render an intelligible representation in the next question.

Output: Save the matrix F, points pts1 and pts2 which you used to generate the screenshot to the file q4 1.npz.

In your write-up: Include a screenshot of epipolarMatchGUI with some detected correspondences.

Q4.2 (10 points) Included in this homework is a file data/templeCoords.npz which contains 288 hand-selected points from im1 saved in the variables x1 and y1.

Now, we can determine the 3D location of these point correspondences using the triangulate function. These 3D point locations can then plotted using the Matplotlib or plotly package. Write a script visualize.py, which loads the necessary files from ../data/ to generate the 3D reconstruction using scatter. An example is shown in Figure 6.

Output: Again, save the matrix F, matrices M1, M2, C1, C2 which you used to generate the screenshots to the file q4 2.npz.

In your write-up: Take a few screenshots of the 3D visualization so that the outline of the temple is clearly visible, and include them with your homework submission.

Figure 5: epipolarMatchGUI shows the corresponding point found by calling

epipolarCorrespondence

5 Bundle Adjustment

Q5.1 (15 points) In some real world applications, manually determining correspondences is infeasible and often there will be noisy coorespondances. Fortunately, the RANSAC method seen in class can be applied to the problem of fundamental matrix estimation. Implement the above algorithm with the signature:

[F, inliers] = ransacF(pts1, pts2, M)

where M is defined in the same way as in Section 2 and inliers is a boolean vector of size equivalent to the number of points. Here inliers is set to true only for the points that satisfy the threshold defined for the given fundamental matrix F.

Hints: Use the seven point to compute the fundamental matrix from the minimal set of points. Then compute the inliers, and refine your estimate using all the inliers.

Q5.2 (15 points)

So far we have independently solved for camera matrix, Mj and 3D projections, Pi. In bundle adjustment, we will jointly optimize the reprojection error with respect to the points Pi and the camera matrix Mj.

err = Xkpij − Proj(Cj,Pi)k2

ij

where Cj = KjMj, same as in Q3.2.

For this homework we are going to only look at optimizing the extrinsic matrix. To do this we will be parametrizing the rotation matrix R using Rodrigues formula to produce vector r ∈ R3. Write a function that converts a Rodrigues vector r to a rotation matrix R

R = rodrigues(r) as well as the inverse function that converts a rotation matrix R to a Rodrigues vector r r = invRodrigues(R)

Figure 6: An example point cloud

Q5.3 (10 points)

Using this parameterization, write an optimization function residuals = rodriguesResidual(K1, M1, p1, K2, p2, x)

where x is the flattened concatenation of P, r2 , and t2 . P are the 3D points; r2 and t2 are the rotation (in the Rodrigues vector form) and translation vectors associated with the projection matrix M2. The residuals are the difference between original image projections and estimated projections (the square of 2-norm of this vector corresponds to the error we computed in Q3.2):

residuals = numpy.concatenate([(p1-p1 hat).reshape([-1]), (p2-p2 hat).reshape([-1])])

Use this error function and Scipy’s nonlinear least square optimizer leastsq write a function to optimize for the best extrinsic matrix and 3D points using the inlier correspondences from some corresp noisy.npz and the RANSAC estimate of the extrinsics and 3D points as an initialization.

[M2, P] = bundleAdjustment(K1, M1, p1, K2, M2 init, p2, P init)

In your write-up: include an image of the original 3D points and the optimized points as well as the reprojection error with your initial M2 and P, and with the optimized matrices.

6 Deliverables

If your andrew id is &lt;ustid-login&gt;, your submission should be the writeup &lt;ustid-login&gt;.pdf contained in a zip file &lt;ustid-login&gt;.zip. Please submit the zip file to CANVAS. The zip file should include the following directory structure:

• submission.py: your implementation of algorithms.

• findM2.py: script to compute the correct camera matrix.

• visualize.py: script to visualize the 3d points.

• q21.npz: file with output of Q2.1.

• q22.npz: file with output of Q2.2.

• q33.npz: file with output of Q3.3.

• q41.npz: file with output of Q4.1.

• q42.npz: file with output of Q4.2.

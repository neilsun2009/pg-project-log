# Week 7
## 16/10/2018
### Update on Particle Filters
1. Add **measurements** and **sigma** into the property list of class **ParticleFilter**.
2. Change some public properties into private and add getter/setter to them.
3. Ensure the sizes of sensors and measurements are consistent.
4. The updated classes, members & methods: 
    * **Particle**: Representation of one particle.
      + Point pos: position
      + double weight: weight
      + Particle(Point pos, double weight): initialize a particle.
      + Point getPos(): get position.
      + double getWeight(): get weight.
      + void randomMove(double radius): move the particle randomly within a given radius.
      + void setWeight(double weight): set a new weight.
      + double probability(Point[] sensors,double sigma, double[] measurements): calculate the posterior probability
    * **ParticleFilter**: A set of particles combining into one filter.
      + Particle[] particles: set of particles.
      + int count: number of particles.
      + Point[] sensors: locations of sensors.
      + double[] measurements: list of measurements.
      + double sigma: sigma in Gaussian.
      + double radius: radius for the particles to be randomly placed.
      + ParticleFilter(int count, Point center, double radius, Point[] sensors, double[] measurements, double sigma) *throws IllegalArgumentException*: initialize a set of particles.
      + void reassignWeights(): // reassign normalized weights
      + Point estimate(): get estimated location.
      + void resample(): resample based on the weights.
      + *private* double[] calProbability(): calculate probabilities of all particles with regards of sensors.
    * **Utils**: A class with static math methods.
      + *static* double distance(Point p1, Point p2): Euclidean distance.
      + *static* double gaussian(double mu, double sigma, double x): Gaussian probability.
    * **Point**: Point in a 2-d coordinate.
      + double x, y: co-ordinates.
      + Point(double x, double y), Point(Point p): construct function.
## 18/10/2018
### Trilateration Implementation
1. Reference on the official tutorial of Apache Math3 library on least squares [1]. Use Levenberg–Marquardt algorithm.
2. Class **Trilateration**:
    + Vector2D[] points: Coordinates of the reference points.
    + double[] distances: Distances from the reference points.
    + Trilateration(double[][] points, double[] distances): Construct function.
    + double[] calculate(double[] startPoint): Calculate the estimated point starting from the start point.
3. Git repository: https://github.com/neilsun2009/trilateration
4. Remaining problems: given a start point that is way far from the actual value, the algorithm may return a wrong point, or even worse, the algorithm may break down as the matrix is unable to perform QR decomposition. Consider using a LSQ method to initialize the starting point.

### Reference
1. Least Squares http://commons.apache.org/proper/commons-math/userguide/leastsquares.html
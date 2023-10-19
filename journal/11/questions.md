# A bit more CSharp and SQL
1. What does ***inheritance*** accomplish for us in C#?

  > inheritance allows us to create a new class from another class, this allows us to extend the functionality of other some classes.

2. How does ***member inheritance*** work in C#? Does a `Class` inherit all members of the base `Class`?

  > Member inheritance allows us to create a new class from a parent class.

3. How does ***accessibility*** affect inheritance?

  > Accessibility affects inheritance by allowing certain classes to be accessible to other classes or not.

4. What is the difference between a `PRIMARY KEY` and a `FOREIGN KEY`

  > A Primary key is a key where the data is sorted in the database. A foreign key is a key that references another table.

5. What is an ***alias***?

  > An alias is a way to refernce something by using the name you alias the code out as.

6. Demonstrate how you would query a join statement that would get all of a doctors patients from the following collections:

  ```SQL
  CREATE TABLE doctors (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patients (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patient_doctors (
    id INT NOT NULL AUTO_INCREMENT,
    doctorId INT NOT NULL,
    patientId INT NOT NULL,

    FOREIGN KEY (doctorId)
      REFERENCES doctors(id),
    FOREIGN KEY (patientId)
      REFERENCES patients(id),
  )

  ```

  > SELECT
    pat-doc.*,
    pat.*
    FROM patient_doctors pat-doc WHERE doctorId = @doctorId
    JOIN patients pat ON patients

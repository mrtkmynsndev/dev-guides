
# Code Review Checklist

## Readability and Maintainability 📖

**Purpose:** Enhances code maintainability and collaboration by ensuring a consistent and readable codebase.

- Code follows project coding style and conventions.
- Variable and function names are meaningful.
- Code is easy to read and understand.
- Consistent indentation and formatting.

```go
// Readability and Maintainability
func main() {
	// Function with meaningful name
	result := divide(5, 10)
	fmt.Println(result)
}

func divide(a, b int) (int, err) {
	if b == 0 {
		return errors.New("Division by zero is not allowed.")
	}
	return a / b
}
```

## Functionality and Correctness ✔️

**Purpose:** Verifies that the code behaves as expected, handles errors correctly, and meets project requirements.

- Code meets requirements and specifications.
- Code has been tested with various scenarios.
- Error handling is appropriate and effective.

```go

// Functionality and Correctness
func main() {
	result := sum(5, 10)
	fmt.Println(result)
}

func sum(numbers []int) (int, err) {
	if numbers == nil{
		return errors.New("numbers are empty.")
	}

	sum := 0
	for _, n := range numbers{
		sum+=i
	}

	return sum
}

```

## Code Structure and Organization 🧩

**Purpose:** Improves code maintainability and promotes a modular and efficient code structure.

- Code is logically organized and modular.
- Proper use of functions, classes, and modules.
- Avoidance of code duplication.


```go

package user // Code is logically organized and modular.

import "fmt"

// Proper use of class
type User struct {
	email    string 
	password string 
	fullName string 
}

func New(email, password, fullName string) (User, error){
	if email == ""{
		return errors.New("email is empty.")
	}
	if password == ""{
		return errors.New("password is empty.")
	}
	if fullName == ""{
		return errors.New("fullName is empty.")
	}

	return User{
		email: email,
		password: password,
		fullName: fullName
	}
}

//Proper use of functions

// Email is a getter for User.email
func (u *User) Email() string {
	return u.email
}

// FullName is a getter for User.FullName
func (u *User) FullName(email string) {
	return u.fullName
}

// Password is a getter for User.Password
func (u *User) Password(email string) {
	return u.password
}

```

## Performance 🕒
**Purpose:** Ensures efficient code execution and addresses performance concerns for optimal application performance.

- Evaluate time and space complexity.
- Identify and discuss potential performance bottlenecks.


```go

import "repository"

// Performance
func main() {
	users := repository.GetUsers()
	userKeys := getUserKeys(users)
	fmt.Println(result)
}

func getUserKeys(users map[string]int) []string {
	// using make([]string, 0, len(count)) instead of make([]string, 0)
	keys := make([]string, 0, len(count)) // Identify and discuss potential performance bottlenecks.
	for k, v := range users{
		keys = append(keys, k)
	}

	return keys
}

```

## Security 🔒

**Purpose:** Protects the application and user data by identifying and mitigating potential security risks.

- Check for security vulnerabilities.
- Ensure proper input validation.
- Sensitive information is handled securely.


```go

// Security
func main() {
	securePassword, err := generatePassword("random-password)"
	if err != nil{
		log.Fatal(err)
	}
	fmt.Println(securePassword)
}

func generatePassword(password string) (string, error) {
	// Proper input validation
	if len(input) < 8 {
		return "", errors.New("Input must be at least 8 characters long.")
	}

	// Secure handling of sensitive information (e.g., password hashing)
	hashedPassword := hashPassword(input)
}

```

## Documentation 📝

**Purpose:** Facilitates code understanding, collaboration, and knowledge transfer through comprehensive documentation.

- Code is adequately documented with comments and inline documentation.
- README and other documentation are updated.

```go

package main

import "fmt"

// User struct represents information about a user.
type User struct {
    ID   int
    Name string
    Age  int
}

// Documentation

// main is the entry point of the program.
func main() {
    // Create a user instance
    newUser := User{
        ID:   1,
        Name: "Mert Kimyonsen",
        Age:  32,
    }

    // Calculate and print the age in months
    ageInMonths := calculateAgeInMonths(newUser)
    fmt.Printf("%s's age in months: %d\n", newUser.Name, ageInMonths)
}

// calculateAgeInMonths calculates the age of a user in months.
func calculateAgeInMonths(user User) int {
    // Assuming 12 months in a year
    return user.Age * 12
}

```

## Testing 🧪

**Purpose:** Ensures code correctness, identifies critical bugs, and maintains the integrity of existing functionality

- Code includes unit tests.
- Tests cover critical functionality.
- Code changes do not break existing tests.

```go

// Testing
// Code includes unit tests.
func Test_Sum(t *testing.T) {
	expected := 7
	calculator := Calculator{}

	result := calculator.Sum(3, 4)
	if got := calculator.Sum(3, 4); got != expected {
		t.Errorf("Expected result to be 7, got %d", result)
	}

}

```

## Scalability 📈

**Purpose:** Prepares the codebase for future expansion and identifies scalable solutions for optimal performance.

- Consider scalability for future growth.
- Discuss potential improvements for scalability.

## Code Review Etiquette 💬

**Purpose:** Fosters a positive and collaborative team culture, ensuring effective communication during code reviews.

- Provide constructive feedback.
- Focus on the code, not the person.
- Maintain a respectful and considerate tone.

## Knowledge Transfer 🧠

**Purpose:** Promotes shared understanding, collaboration, and knowledge sharing within the development team.

- Ensure changes are understood by the team.
- Share knowledge about the codebase and design decisions.

## Version Control ⚙️

**Purpose:** Maintains a clear history of changes, aids in tracking modifications, and ensures a consistent development workflow.

- Commits are logically organized.
- Commit messages are clear and descriptive.
- Adherence to the version control process.

## Dependencies and Third-Party Libraries ➕

**Purpose:** Ensures proper justification, documentation, and licensing compliance for third-party dependencies.*

- Check necessity and documentation of new dependencies.
- Verify compatibility of third-party library licenses.

## Consistency with Coding Standards 📏

**Purpose:** Enhances codebase maintainability and readability by adhering to established coding standards and best practices.

- Ensure code aligns with coding standards and best practices.

## Feedback Loop 🔄

**Purpose:** Promotes open communication, clarification, and timely resolution of issues during the code review process.

- Establish an effective feedback loop with the author.
- Address questions and concerns promptly.

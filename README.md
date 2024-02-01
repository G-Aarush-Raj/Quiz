#QUIZ
    
    
    
    def run_quiz():
        print("1. Standard Quiz")
        print("2. Custom Quiz")
        choice = input("Enter your choice (1 or 2): ")
        if choice == "1":
            print("\nWelcome to the Standard Quiz Game!")
            quiz(questions, options)
        elif choice == "2":
            custom_quiz()
        else:
            print("Invalid choice. Please enter 1 or 2.")
    
    def quiz(questions, options):
        score = 0
        for i, (j, k) in enumerate(questions.items()):
            print(j)
            for l, option in enumerate(options[i]):
                print(l+1,option,end="\n")
            user = input("Choose the correct answer, enter the number: ")
            if user.isdigit() and 1 <= int(user) <= len(options[i]):
                userAnswer = int(user) - 1
                if userAnswer == k:
                    print("Correct!")
                    score += 1
                else:
                    correct = options[i][k]
                    print("Wrong! The correct answer is ",correct)
            else:
                print("Invalid input. Please enter a valid option.")
        print("Your score is", score, "out of", len(questions))
    
    def custom_quiz():
        c_questions = {}
        c_options = []
        c_ques = int(input("Enter the number of custom questions you want to add: "))
        for _ in range(c_ques):
            q = input("Enter the question: ")
            a = int(input(f"Enter the correct option number : ")) - 1
            options = [input(f"Enter option {i + 1}: ") for i in range(4)]
            c_questions[q] = a
            c_options.append(options)
        print("\nLet's try your custom quiz!")
        quiz(c_questions, c_options)
    print("Welcome to the Quiz Game!")
    options = [
        ["Paris", "New Delhi", "Dhaka", "Tokyo"],
        ["Mars", "Earth", "Venus", "Pluto"],
        ["Elephant", "Horse", "Blue Whale", "Kangaroo"],
        ["7", "9", "10", "8"]
    ]
    questions = {
        "What is the capital of India?": 1,
        "Which planet is known as the Red Planet?": 0,
        "What is the largest mammal in the world?": 2,
        "What is the square root of 81?": 1
    }
    run_quiz()
        

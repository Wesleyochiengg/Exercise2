#include <iostream>

class BankAccount {
private:
    double balance;

public:
    BankAccount() : balance(0) {}

    void deposit(double amount) {
        balance += amount;
    }

    void withdraw(double amount) {
        if (amount > balance) {
            std::cout << "Insufficient funds for withdrawal." << std::endl;
        } else {
            balance -= amount;
        }
    }

    double getBalance() const {
        return balance;
    }
};

int main() {
    BankAccount account;

    account.deposit(500);
    account.withdraw(200);
    account.withdraw(400);

    std::cout << "Final balance: $" << account.getBalance() << std::endl;

    return 0;
}


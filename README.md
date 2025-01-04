# Study Notes
### Polymorphism
- Polymorphism means many forms, it allows one interface to have multiple implementations
 // Base class
public virtual class Payment {
    public virtual String processPayment() {
        return 'Processing generic payment';
    }
}


public class CreditCardPayment extends Payment {
    public override String processPayment() {
        return 'Processing credit card payment';
    }
}

public class PayPalPayment extends Payment {
    public override String processPayment() {
        return 'Processing PayPal payment';
    }
}

// Implementation
public class PaymentProcessor {
    public void handlePayment(Payment payment) {
        System.debug(payment.processPayment());
    }
}

// Test
PaymentProcessor processor = new PaymentProcessor();
processor.handlePayment(new CreditCardPayment()); // Output: Processing credit card payment
processor.handlePayment(new PayPalPayment());     // Output: Processing PayPal payment

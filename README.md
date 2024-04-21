@startuml

class Menu {
    - menuItems: List<Item>
    - categories: List<Category>
    + addItem()
    + removeItem()
    + searchItemByName()
    + generateMenu()
}

class FoodMenu {
    - specials: List<Item>
    - popularItems: List<Item>
    + addSpecials()
    + removeSpecials()
    + addPopularItems()
    + removePopularItems()
}

class StationaryMenu {
    - officeEssentials: List<Item>
    - craftSupplies: List<Item>
    + addOfficeEssentials()
    + addCraftSupplies()
}

class Customer {
    - customerId: String
    - name: String
    - email: String
    - address: String
    - phoneNumber: String
    + register()
    + login()
    + updateProfile()
}

class Student {
    - studentId: String
    - batch: String
    - major: String
    + register()
    + login()
    + updateProfile()
}

class Staff {
    - staffId: String
    - department: String
    - position: String
    - officeLocation: String
    + register()
    + login()
    + updateProfile()
}

class Delivery {
    - orderId: String
    - deliveryAddress: String
    - deliveryTime: DateTime
    - deliveryStatus: String
    + assignDeliveryPersonnel()
    + updateDeliveryStatus()
    + calculateEstimatedDeliveryTime()
    + trackDelivery()
}

class Order {
    - orderId: String
    - customer: Customer
    - products: List<Item>
    - totalPrice: float
    - status: String
    + addProduct()
    + removeProduct()
    + calculateTotalPrice()
    + updateStatus()
}

class FoodOrder {
    - deliveryAddress: String
    - deliveryTime: DateTime
    - specialInstructions: String
    + setDeliveryAddress()
    + setDeliveryTime()
    + setSpecialInstructions()
}

class StationaryOrder {
    - pickupLocation: String
    - pickupTime: DateTime
    - quantity: int
    + setPickupLocation()
    + setPickupTime()
    + setQuantity()
}

class Employee {
    - employeeId: String
    - firstName: String
    - lastName: String
    - role: String
    - phoneNumber: String
    - email: String
    - address: String
    - hourlyWage: float
    - employmentStatus: String
    + updateContactInfo()
    + calculateSalary()
    + processPayment()
    + assignTask()
    + requestLeave()
    + viewSchedule()
}

class Manager {
    - department: String
    - bonus: float
    + calculateSalary()
    + conductPerformanceReviews()
    + conductMeeting()
}

class FullTimeEmployee {
    - annualSalary: float
    - bonusEarned: float
    + calculateSalary()
    + calculateBonus()
}

class PartTimeEmployee {
    - hoursWorked: float
    - overtimeHours: float
    + calculateSalary()
    + calculateOvertimePay()
}

class Intern {
    - internshipDuration: int
    - mentorName: String
    + requestLeave()
    + completeInternship()
}

class RemoteEmployee {
    - remoteLocation: String
    - remoteWorkHours: float
    + updateContactInfo()
    + viewSchedule()
}

class LocationTracker {
    - latitude: float
    - longitude: float
    - address: String
}

class GPSLocationTracker {
    - gpsAccuracy: float
    - signalStrength: int
    + trackLocation()
}

class Inventory {
    - items: List<Item>
    - threshold: int
    - restockQuantity: int
    - restockThreshold: int
    + addItem()
    + removeItem()
    + updateItemQuantity()
    + checkThreshold()
    + restockItem()
    + generateInventoryReport()
    + getLowStockItems()
    + updateRestockThreshold()
}

class FoodInventory {
    // Specific attributes and methods for food inventory
}

class StationaryInventory {
    // Specific attributes and methods for stationary inventory
}

class Payment {
    - paymentId: String
    - orderId: String
    - amount: float
    - paymentMethod: String
    + processPayment()
}

class CreditCardPayment {
    - cardNumber: String
    - expiryDate: Date
}

class JazzCashPayment {
    - jazzCashId: String
    - transactionId: String
    - balance: float
}

class Transaction {
    - transactionId: String
    - orderId: String
    - transactionDate: DateTime
    - paymentMethod: String
    - amount: float
    + processTransaction()
    + getTransactionDetails()
    + generateTransactionReceipt()
    + calculateTotalSales()
}

class OnlineTransaction {
    - transactionPlatform: String
}

class Discount {
    - discountId: String
    - discountAmount: float
    - validity: Date
    + applyDiscount()
}

class StudentDiscount {
    - discountPercentage: float
    - validityPeriod: Date
    - applicableItems: List<Item>
}

class BulkDiscount {
    - minimumQuantity: int
    - discountAmount: float
    - applicableCategories: List<Category>
}

class PromotionDeal {
    - dealId: String
    - dealName: String
    - startDate: Date
    - endDate: Date
    - discountPercentage: float
    - applicableItems: List<Item>
    + createDeal()
    + updateDeal()
    + deleteDeal()
    + applyDealToOrder()
}

class Reporting {
    - reportId: String
    - reportType: String
    - generatedBy: Employee
    + generateReport()
}

class SalesReport {
    - salesData: List<Sale>
    - dateRange: DateRange
    - topSellingProducts: List<Item>
}

class FeedbackReport {
    - feedbackData: List<Feedback>
    - rating: float
    - improvementSuggestions: String
}

class Voucher {
    - voucherCode: String
    - discountAmount: float
    - expiryDate: Date
    - applicableItems: List<Item>
    + generateVoucher()
    + redeemVoucher()
    + checkVoucherValidity()
}

class Feedback {
    - feedbackId: String
    - orderId: String
    - rating: float
    - comment: String
    + submitFeedback()
}

class ProductFeedback {
    - productId: String
    - productRating: float
    - productComment: String
}

class SellerFeedback {
    - sellerId: String
    - sellerRating: float
    - sellerComment: String
}

class Exception {
    + handleException()
    + logException()
}

class Database {
    + connect()
    + query()
    + disconnect()
}

class Main {
    + start()
    + handleEvents()
    + close()
}

Menu <|-- FoodMenu
Menu <|-- StationaryMenu
Customer <|-- Student
Customer <|-- Staff
Order <|-- FoodOrder
Order <|-- StationaryOrder
Employee <|-- Manager
Employee <|-- FullTimeEmployee
Employee <|-- PartTimeEmployee
Employee <|-- Intern
Employee <|-- RemoteEmployee
LocationTracker <|-- GPSLocationTracker
Inventory <|-- FoodInventory
Inventory <|-- StationaryInventory
Payment <|-- CreditCardPayment
Payment <|-- JazzCashPayment
Transaction <|-- OnlineTransaction
Discount <|-- StudentDiscount
Discount <|-- BulkDiscount
PromotionDeal o-- "*" Order
Reporting <|-- SalesReport
Reporting <|-- FeedbackReport
Voucher o-- "*" Order
Feedback <|-- ProductFeedback
Feedback <|-- SellerFeedback

@enduml

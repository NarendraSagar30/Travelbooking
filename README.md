# Travelbooking<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TravelEase - Simple, Transparent Booking</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
        
        .step-indicator {
            transition: all 0.3s ease;
        }
        
        .step-active {
            background: linear-gradient(135deg, #3b82f6, #1d4ed8);
            color: white;
        }
        
        .step-completed {
            background: linear-gradient(135deg, #10b981, #059669);
            color: white;
        }
        
        .booking-card {
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }
        
        .booking-card:hover {
            border-color: #3b82f6;
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(59, 130, 246, 0.1);
        }
        
        .price-breakdown {
            background: linear-gradient(135deg, #f8fafc, #e2e8f0);
        }
        
        .progress-bar {
            background: linear-gradient(90deg, #3b82f6, #1d4ed8);
            transition: width 0.5s ease;
        }
        
        .fade-in {
            animation: fadeIn 0.5s ease-in;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="bg-gray-50 min-h-screen">
    <!-- Header -->
    <header class="bg-white shadow-sm border-b">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex items-center space-x-2">
                    <div class="w-8 h-8 bg-gradient-to-r from-blue-600 to-blue-800 rounded-lg flex items-center justify-center">
                        <span class="text-white font-bold text-sm">T</span>
                    </div>
                    <span class="text-xl font-bold text-gray-900">TravelEase</span>
                </div>
                <div class="flex items-center space-x-4">
                    <span class="text-sm text-gray-600">Need help? Call (555) 123-4567</span>
                    <button class="bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700 transition-colors">
                        Sign In
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Progress Indicator -->
    <div class="bg-white border-b">
        <div class="max-w-4xl mx-auto px-4 py-4">
            <div class="flex items-center justify-between mb-2">
                <div class="flex items-center space-x-8">
                    <div class="flex items-center space-x-2">
                        <div class="step-indicator step-active w-8 h-8 rounded-full flex items-center justify-center text-sm font-medium">1</div>
                        <span class="text-sm font-medium text-blue-600">Search</span>
                    </div>
                    <div class="flex items-center space-x-2">
                        <div class="step-indicator w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center text-sm font-medium text-gray-500">2</div>
                        <span class="text-sm text-gray-500">Select</span>
                    </div>
                    <div class="flex items-center space-x-2">
                        <div class="step-indicator w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center text-sm font-medium text-gray-500">3</div>
                        <span class="text-sm text-gray-500">Details</span>
                    </div>
                    <div class="flex items-center space-x-2">
                        <div class="step-indicator w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center text-sm font-medium text-gray-500">4</div>
                        <span class="text-sm text-gray-500">Payment</span>
                    </div>
                </div>
            </div>
            <div class="w-full bg-gray-200 rounded-full h-2">
                <div class="progress-bar h-2 rounded-full" style="width: 25%"></div>
            </div>
        </div>
    </div>

    <!-- Main Content -->
    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        <!-- Search Section -->
        <div id="searchSection" class="fade-in">
            <div class="text-center mb-8">
                <h1 class="text-3xl font-bold text-gray-900 mb-2">Find Your Perfect Trip</h1>
                <p class="text-gray-600">Transparent pricing, no hidden fees, simple booking</p>
            </div>

            <!-- Search Form -->
            <div class="bg-white rounded-xl shadow-lg p-6 mb-8">
                <div class="grid grid-cols-1 md:grid-cols-4 gap-4 mb-4">
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-2">From</label>
                        <input type="text" placeholder="New York (NYC)" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-2">To</label>
                        <input type="text" placeholder="Los Angeles (LAX)" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-2">Departure</label>
                        <input type="date" value="2024-02-15" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-2">Passengers</label>
                        <select class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            <option>1 Adult</option>
                            <option>2 Adults</option>
                            <option>3 Adults</option>
                        </select>
                    </div>
                </div>
                <button onclick="searchFlights()" class="w-full bg-gradient-to-r from-blue-600 to-blue-700 text-white py-3 px-6 rounded-lg font-medium hover:from-blue-700 hover:to-blue-800 transition-all">
                    Search Flights
                </button>
            </div>

            <!-- Trust Indicators -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
                <div class="text-center">
                    <div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-3">
                        <span class="text-green-600 text-xl">✓</span>
                    </div>
                    <h3 class="font-semibold text-gray-900 mb-1">No Hidden Fees</h3>
                    <p class="text-sm text-gray-600">All taxes and fees included in displayed prices</p>
                </div>
                <div class="text-center">
                    <div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-3">
                        <span class="text-blue-600 text-xl">🔒</span>
                    </div>
                    <h3 class="font-semibold text-gray-900 mb-1">Secure Booking</h3>
                    <p class="text-sm text-gray-600">256-bit SSL encryption protects your data</p>
                </div>
                <div class="text-center">
                    <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mx-auto mb-3">
                        <span class="text-purple-600 text-xl">⚡</span>
                    </div>
                    <h3 class="font-semibold text-gray-900 mb-1">Instant Confirmation</h3>
                    <p class="text-sm text-gray-600">Get your tickets immediately after booking</p>
                </div>
            </div>
        </div>

        <!-- Flight Results Section (Hidden initially) -->
        <div id="resultsSection" class="hidden">
            <div class="flex justify-between items-center mb-6">
                <h2 class="text-2xl font-bold text-gray-900">Available Flights</h2>
                <div class="flex items-center space-x-4">
                    <span class="text-sm text-gray-600">Sort by:</span>
                    <select class="border border-gray-300 rounded-lg px-3 py-2 text-sm">
                        <option>Best Value</option>
                        <option>Lowest Price</option>
                        <option>Shortest Duration</option>
                    </select>
                </div>
            </div>

            <!-- Flight Options -->
            <div class="space-y-4 mb-8">
                <!-- Flight 1 -->
                <div class="booking-card bg-white rounded-xl shadow-md p-6">
                    <div class="flex items-center justify-between">
                        <div class="flex items-center space-x-6">
                            <div class="text-center">
                                <div class="text-lg font-bold text-gray-900">8:00 AM</div>
                                <div class="text-sm text-gray-500">NYC</div>
                            </div>
                            <div class="flex-1 relative">
                                <div class="border-t-2 border-gray-300"></div>
                                <div class="absolute top-0 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-white px-2">
                                    <span class="text-xs text-gray-500">5h 30m</span>
                                </div>
                            </div>
                            <div class="text-center">
                                <div class="text-lg font-bold text-gray-900">11:30 AM</div>
                                <div class="text-sm text-gray-500">LAX</div>
                            </div>
                        </div>
                        <div class="text-right">
                            <div class="text-2xl font-bold text-gray-900">$299</div>
                            <div class="text-sm text-green-600 font-medium">✓ All fees included</div>
                            <button onclick="selectFlight(1)" class="mt-2 bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition-colors">
                                Select
                            </button>
                        </div>
                    </div>
                    <div class="mt-4 pt-4 border-t border-gray-100">
                        <div class="flex items-center justify-between text-sm text-gray-600">
                            <span>American Airlines • Economy</span>
                            <span>Non-stop</span>
                            <button onclick="toggleBreakdown(1)" class="text-blue-600 hover:text-blue-700">View price breakdown</button>
                        </div>
                        <div id="breakdown1" class="hidden mt-3 price-breakdown rounded-lg p-4">
                            <div class="space-y-2 text-sm">
                                <div class="flex justify-between">
                                    <span>Base fare</span>
                                    <span>$249</span>
                                </div>
                                <div class="flex justify-between">
                                    <span>Taxes & fees</span>
                                    <span>$50</span>
                                </div>
                                <div class="border-t pt-2 font-semibold flex justify-between">
                                    <span>Total</span>
                                    <span>$299</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Flight 2 -->
                <div class="booking-card bg-white rounded-xl shadow-md p-6">
                    <div class="flex items-center justify-between">
                        <div class="flex items-center space-x-6">
                            <div class="text-center">
                                <div class="text-lg font-bold text-gray-900">2:15 PM</div>
                                <div class="text-sm text-gray-500">NYC</div>
                            </div>
                            <div class="flex-1 relative">
                                <div class="border-t-2 border-gray-300"></div>
                                <div class="absolute top-0 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-white px-2">
                                    <span class="text-xs text-gray-500">6h 45m</span>
                                </div>
                            </div>
                            <div class="text-center">
                                <div class="text-lg font-bold text-gray-900">6:00 PM</div>
                                <div class="text-sm text-gray-500">LAX</div>
                            </div>
                        </div>
                        <div class="text-right">
                            <div class="text-2xl font-bold text-gray-900">$259</div>
                            <div class="text-sm text-green-600 font-medium">✓ All fees included</div>
                            <button onclick="selectFlight(2)" class="mt-2 bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition-colors">
                                Select
                            </button>
                        </div>
                    </div>
                    <div class="mt-4 pt-4 border-t border-gray-100">
                        <div class="flex items-center justify-between text-sm text-gray-600">
                            <span>Delta Airlines • Economy</span>
                            <span>1 stop (1h 20m)</span>
                            <button onclick="toggleBreakdown(2)" class="text-blue-600 hover:text-blue-700">View price breakdown</button>
                        </div>
                        <div id="breakdown2" class="hidden mt-3 price-breakdown rounded-lg p-4">
                            <div class="space-y-2 text-sm">
                                <div class="flex justify-between">
                                    <span>Base fare</span>
                                    <span>$209</span>
                                </div>
                                <div class="flex justify-between">
                                    <span>Taxes & fees</span>
                                    <span>$50</span>
                                </div>
                                <div class="border-t pt-2 font-semibold flex justify-between">
                                    <span>Total</span>
                                    <span>$259</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Booking Details Section (Hidden initially) -->
        <div id="detailsSection" class="hidden">
            <h2 class="text-2xl font-bold text-gray-900 mb-6">Passenger Details</h2>
            
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                <div class="lg:col-span-2">
                    <div class="bg-white rounded-xl shadow-md p-6 mb-6">
                        <h3 class="text-lg font-semibold text-gray-900 mb-4">Passenger Information</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">First Name *</label>
                                <input type="text" placeholder="John" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Last Name *</label>
                                <input type="text" placeholder="Doe" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Email *</label>
                                <input type="email" placeholder="john@example.com" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Phone *</label>
                                <input type="tel" placeholder="+1 (555) 123-4567" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                        </div>
                    </div>

                    <div class="bg-white rounded-xl shadow-md p-6">
                        <h3 class="text-lg font-semibold text-gray-900 mb-4">Add-ons (Optional)</h3>
                        <div class="space-y-4">
                            <label class="flex items-center space-x-3 cursor-pointer">
                                <input type="checkbox" class="w-5 h-5 text-blue-600 rounded">
                                <div class="flex-1">
                                    <div class="font-medium text-gray-900">Seat Selection</div>
                                    <div class="text-sm text-gray-600">Choose your preferred seat</div>
                                </div>
                                <div class="text-gray-900 font-medium">+$25</div>
                            </label>
                            <label class="flex items-center space-x-3 cursor-pointer">
                                <input type="checkbox" class="w-5 h-5 text-blue-600 rounded">
                                <div class="flex-1">
                                    <div class="font-medium text-gray-900">Extra Baggage</div>
                                    <div class="text-sm text-gray-600">Additional 23kg checked bag</div>
                                </div>
                                <div class="text-gray-900 font-medium">+$35</div>
                            </label>
                            <label class="flex items-center space-x-3 cursor-pointer">
                                <input type="checkbox" class="w-5 h-5 text-blue-600 rounded">
                                <div class="flex-1">
                                    <div class="font-medium text-gray-900">Travel Insurance</div>
                                    <div class="text-sm text-gray-600">Trip cancellation & medical coverage</div>
                                </div>
                                <div class="text-gray-900 font-medium">+$45</div>
                            </label>
                        </div>
                    </div>
                </div>

                <!-- Booking Summary -->
                <div class="lg:col-span-1">
                    <div class="bg-white rounded-xl shadow-md p-6 sticky top-4">
                        <h3 class="text-lg font-semibold text-gray-900 mb-4">Booking Summary</h3>
     

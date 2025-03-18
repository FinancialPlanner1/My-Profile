import React, { useState } from 'react';
import { Card, CardContent } from '@/components/ui/card';
import { ChevronDown, ChevronUp } from 'lucide-react';

const Dropdown = ({ title, children }) => {
    const [isOpen, setIsOpen] = useState(false);

    return (
        <div className="mb-4">
            <div 
                className="flex justify-between items-center bg-blue-600 text-white p-4 rounded-2xl cursor-pointer"
                onClick={() => setIsOpen(!isOpen)}
            >
                <h2 className="text-xl font-bold">{title}</h2>
                {isOpen ? <ChevronUp /> : <ChevronDown />}
            </div>
            {isOpen && (
                <div className="p-4 bg-white border border-gray-200 rounded-2xl mt-2">
                    {children}
                </div>
            )}
        </div>
    );
};

const FinancialPlannerProfile = () => {
    return (
        <div className="max-w-3xl mx-auto p-4">
            <Card>
                <CardContent>
                    <h1 className="text-3xl font-bold mb-4 text-center">William Meyer</h1>
                    <h2 className="text-lg mb-2 text-center">Financial Planner</h2>

                    <Dropdown title="Contact Me">
                        <p>Email: w.meyer@sanlam4u.co.za</p>
                        <p>Cell: +27 63 422 9601</p>
                    </Dropdown>

                    <Dropdown title="About Me">
                        <p>
                            As a financial planner, I am dedicated to helping clients build wealth and create a lasting legacy through personalised strategies and informed decision making.
                            I focus on understanding each client’s unique needs, offering clear actionable advice and building long term plans for success. By providing tailored solutions, I empower clients to navigate life’s financial challenges with confidence and security.
                        </p>
                    </Dropdown>

                    <Dropdown title="Qualifications">
                        <ul className="list-disc pl-4">
                            <li>BCom in Business Management</li>
                            <li>2 Years of Experience in the Financial Planning industry</li>
                            <li>Authorised Financial Planner at Sanlam</li>
                        </ul>
                    </Dropdown>

                    <Dropdown title="Services Offered">
                        <ul className="list-disc pl-4">
                            <li>Life Insurance</li>
                            <li>Retirement Planning</li>
                            <li>Tax-Free Investment</li>
                            <li>Will & Estate Planning</li>
                            <li>Investment Advice & Solutions</li>
                        </ul>
                    </Dropdown>

                    <Dropdown title="Location">
                        <p>Find me at: 1st Floor, Century Way, The Colosseum, Cape Town, South Africa</p>
                    </Dropdown>

                    <Dropdown title="Book a Meeting">
                        <form className="space-y-4">
                            <input type="text" placeholder="Name" className="w-full p-2 border rounded-xl" />
                            <input type="text" placeholder="Surname" className="w-full p-2 border rounded-xl" />
                            <input type="email" placeholder="Email" className="w-full p-2 border rounded-xl" />
                            <input type="text" placeholder="Contact Number" className="w-full p-2 border rounded-xl" />
                            <textarea placeholder="Additional Details (Optional)" className="w-full p-2 border rounded-xl"></textarea>
                            <button className="bg-blue-600 text-white p-2 rounded-xl w-full">Send Meeting Request</button>
                        </form>
                    </Dropdown>

                    <Dropdown title="Connect with Me">
                        <p>Connect on <a href="#" className="text-blue-600 underline">LinkedIn</a></p>
                    </Dropdown>
                </CardContent>
            </Card>
        </div>
    );
};

export default FinancialPlannerProfile;

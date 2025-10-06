import React, { useState } from "react";
import "./App.css";
import sam from './assets/pic1.jpg';
import prawin from './assets/pic2.jpg';
import bala from './assets/pic3.jpg';
import saran from './assets/pic4.jpg';
import fazil from './assets/pic5.jpg';
import jeeva from './assets/pic6.jpg';
import ashwin from './assets/mapla.jpg';
import th from './assets/pic8.jpg';

function App() {
  const [searchTerm, setSearchTerm] = useState("");
  const employeesData = [
  { id: 1, name: "Prawin", department: "HR", role: "Manager",image:prawin },
  { id: 2, name: "Bala", department: "IT", role: "Developer" ,image:bala},
  { id: 3, name: "Saran", department: "Finance", role: "Analyst",image:saran },
  { id: 4, name: "Fazil", department: "IT", role: "Developer",image:fazil },
  { id: 5, name: "Sam Nitish", department: "IT",role:"CEO",image:sam},
   { id: 6, name: "Jeeva", department: "IT",role:"developer",image:jeeva},
    { id: 7, name: "Ashwin", department: "IT",role:"CEO assistant",image:ashwin},
     { id: 8, name: "Thanzeer", department: "IT",role:"worker",image:th}
];


  const filteredEmployees = employeesData.filter(
    (employee) =>
      employee.name.toLowerCase().includes(searchTerm.toLowerCase()) ||
      employee.department.toLowerCase().includes(searchTerm.toLowerCase()) ||
      employee.role.toLowerCase().includes(searchTerm.toLowerCase())
  );

  return (
    <div className="app">
      <h1>Employee Directory</h1>
      <input
        type="text"
        placeholder="Search employees..."
        value={searchTerm}
        onChange={(e) => setSearchTerm(e.target.value)}
        className="search-input"
      />
      <div className="employee-list">
        {filteredEmployees.length > 0 ? (
          filteredEmployees.map((emp) => (
            <div key={emp.id} className="employee-card">
              <img src={emp.image} className="image"/>
              <h3>{emp.name}</h3>
              <p>Department: {emp.department}</p>
              <p>Role: {emp.role}</p>
            </div>
          ))
        ) : (
          <p>No employees found.</p>
        )}
      </div>
    </div>
  );
}

export default App;
# sooriyaa

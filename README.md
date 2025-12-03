<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>English Grammar Test</title>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/qrcode@1.5.3/build/qrcode.min.js"></script>
<script src="https://html2canvas.hertzen.com/dist/html2canvas.min.js"></script>
<style>
/* Modern Color System */
:root {
--primary: #3498db;
--primary-glow: #2980b9;
--primary-light: #5dade2;

--accent: #2ecc71;
--accent-glow: #27ae60;
--accent-light: #58d68d;

--secondary: #9b59b6;
--secondary-glow: #8e44ad;
--secondary-light: #bb8fce;

--tertiary: #e74c3c;
--tertiary-glow: #c0392b;
--tertiary-light: #ec7063;

--english-blue: #3498db;
--english-green: #2ecc71;
--english-purple: #9b59b6;
--english-red: #e74c3c;

/* Gradients */
--primary-gradient: linear-gradient(135deg, var(--primary) 0%, var(--primary-glow) 50%, var(--primary-light) 100%);
--accent-gradient: linear-gradient(135deg, var(--accent) 0%, var(--accent-glow) 50%, var(--english-green) 100%);
--secondary-gradient: linear-gradient(135deg, var(--secondary) 0%, var(--secondary-glow) 50%, var(--english-purple) 100%);
--tertiary-gradient: linear-gradient(135deg, var(--tertiary) 0%, var(--tertiary-glow) 50%, var(--english-red) 100%);
--english-gradient: linear-gradient(135deg, var(--english-blue) 0%, var(--english-green) 50%, var(--english-purple) 100%);

/* Glow Effects */
--glow-primary: 0 0 20px rgba(52, 152, 219, 0.7), 0 0 40px rgba(52, 152, 219, 0.5), 0 0 60px rgba(52, 152, 219, 0.3);
--glow-accent: 0 0 20px rgba(46, 204, 113, 0.7), 0 0 40px rgba(46, 204, 113, 0.5), 0 0 60px rgba(46, 204, 113, 0.3);
--glow-secondary: 0 0 20px rgba(155, 89, 182, 0.7), 0 0 40px rgba(155, 89, 182, 0.5), 0 0 60px rgba(155, 89, 182, 0.3);
--glow-tertiary: 0 0 20px rgba(231, 76, 60, 0.7), 0 0 40px rgba(231, 76, 60, 0.5), 0 0 60px rgba(231, 76, 60, 0.3);
--glow-english: 0 0 20px rgba(52, 152, 219, 0.8), 0 0 40px rgba(46, 204, 113, 0.6), 0 0 60px rgba(155, 89, 182, 0.4);

/* Design Variables */
--bg: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
--card-bg: rgba(255, 255, 255, 0.95);
--text: #1F2937;
--light-text: #6B7280;
--border: rgba(52, 152, 219, 0.2);
--shadow: 0 8px 32px rgba(52, 152, 219, 0.1);
--shadow-hover: 0 20px 40px rgba(52, 152, 219, 0.2);
}

.dark-theme {
--bg: linear-gradient(135deg, #0A3D62 0%, #1A5F7A 100%);
--card-bg: rgba(15, 30, 45, 0.95);
--text: #F1F5F9;
--light-text: #CBD5E1;
--border: rgba(52, 152, 219, 0.1);
--shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
--shadow-hover: 0 20px 40px rgba(0, 0, 0, 0.4);
}

* {
box-sizing: border-box;
font-family: 'Tajawal', Tahoma, Arial, sans-serif;
margin: 0;
padding: 0;
}

body {
background: var(--bg);
color: var(--text);
line-height: 1.7;
overflow-x: hidden;
padding-top: 80px;
transition: all 0.5s ease;
min-height: 100vh;
}

/* Header Design */
header {
background: rgba(52, 152, 219, 0.1);
backdrop-filter: blur(20px);
color: white;
position: fixed;
top: 0;
width: 100%;
z-index: 1000;
box-shadow: var(--shadow);
border-bottom: 1px solid var(--border);
padding: 15px 0;
}

.header-container {
max-width: 1200px;
margin: 0 auto;
display: flex;
justify-content: space-between;
align-items: center;
padding: 0 20px;
}

.title-section h1 {
font-size: 1.5rem;
font-weight: 800;
background: var(--accent-gradient);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
text-shadow: 0 2px 10px rgba(52, 152, 219, 0.3);
}

.header-actions {
display: flex;
gap: 10px;
}

.theme-btn, .back-btn {
background: rgba(52, 152, 219, 0.2);
color: white;
border: 2px solid rgba(255, 255, 255, 0.3);
padding: 10px 20px;
border-radius: 15px;
font-weight: 600;
cursor: pointer;
transition: all 0.3s ease;
display: flex;
align-items: center;
gap: 8px;
backdrop-filter: blur(20px);
text-decoration: none;
position: relative;
overflow: hidden;
box-shadow: 0 0 15px rgba(52, 152, 219, 0.3);
}

.theme-btn:hover, .back-btn:hover {
background: rgba(52, 152, 219, 0.3);
transform: translateY(-3px);
box-shadow: 0 0 25px rgba(52, 152, 219, 0.5), 0 5px 20px rgba(0, 0, 0, 0.2);
border-color: rgba(255, 255, 255, 0.5);
}

/* Main Content */
main {
max-width: 1000px;
margin: 30px auto;
padding: 0 20px;
}

/* Hero Section */
.hero-section {
background: linear-gradient(135deg, rgba(52, 152, 219, 0.15), rgba(46, 204, 113, 0.15));
backdrop-filter: blur(30px);
color: white;
border-radius: 24px;
padding: 40px;
margin-bottom: 30px;
text-align: center;
position: relative;
overflow: hidden;
box-shadow: 0 20px 60px rgba(52, 152, 219, 0.15),
inset 0 1px 0 rgba(255, 255, 255, 0.2);
border: 2px solid rgba(255, 255, 255, 0.1);
}

.hero-section::before {
content: "";
position: absolute;
top: 0;
left: 0;
right: 0;
bottom: 0;
background: var(--accent-gradient);
opacity: 0.1;
z-index: -1;
}

.hero-content {
position: relative;
z-index: 1;
}

.hero-title {
font-size: 2.2rem;
font-weight: 800;
background: linear-gradient(135deg, #fff 0%, #f0f0f0 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
}

.hero-subtitle {
font-size: 1.1rem;
margin-bottom: 25px;
opacity: 0.9;
max-width: 600px;
margin-left: auto;
margin-right: auto;
}

/* Student Info Form */
.student-info-form {
background: rgba(255, 255, 255, 0.1);
backdrop-filter: blur(20px);
padding: 25px;
border-radius: 20px;
margin: 25px 0;
border: 1px solid rgba(255, 255, 255, 0.2);
}

.student-info-form h3 {
color: white;
margin-bottom: 20px;
text-align: center;
font-size: 1.5rem;
}

.form-row {
display: flex;
gap: 20px;
margin-bottom: 20px;
flex-wrap: wrap;
}

.input-group {
flex: 1;
min-width: 200px;
}

.input-group label {
display: block;
color: white;
margin-bottom: 8px;
font-weight: 600;
font-size: 1rem;
}

.input-group input {
width: 100%;
padding: 15px;
border-radius: 15px;
border: 2px solid rgba(255, 255, 255, 0.3);
background: rgba(255, 255, 255, 0.1);
color: white;
font-size: 1rem;
transition: all 0.3s ease;
}

.input-group input:focus {
outline: none;
border-color: var(--accent);
box-shadow: 0 0 15px rgba(46, 204, 113, 0.3);
background: rgba(255, 255, 255, 0.15);
}

.student-info-display {
background: rgba(46, 204, 113, 0.15);
backdrop-filter: blur(20px);
padding: 20px;
border-radius: 15px;
margin: 25px 0;
border: 1px solid rgba(46, 204, 113, 0.3);
color: white;
display: flex;
justify-content: space-between;
align-items: center;
flex-wrap: wrap;
gap: 15px;
}

.student-details {
display: flex;
gap: 30px;
flex-wrap: wrap;
}

.student-detail {
display: flex;
flex-direction: column;
}

.student-detail span:first-child {
font-size: 0.9rem;
opacity: 0.8;
margin-bottom: 5px;
}

.student-detail span:last-child {
font-size: 1.1rem;
font-weight: 700;
}

.edit-student-btn {
background: rgba(52, 152, 219, 0.2);
border: 2px solid rgba(52, 152, 219, 0.3);
color: white;
padding: 10px 20px;
border-radius: 10px;
cursor: pointer;
transition: all 0.3s ease;
display: flex;
align-items: center;
gap: 8px;
}

.edit-student-btn:hover {
background: rgba(52, 152, 219, 0.3);
transform: translateY(-2px);
box-shadow: 0 0 15px rgba(52, 152, 219, 0.3);
}

.teacher-info {
background: rgba(52, 152, 219, 0.2);
backdrop-filter: blur(10px);
padding: 10px 20px;
border-radius: 15px;
display: inline-block;
margin-top: 15px;
border: 1px solid rgba(255, 255, 255, 0.1);
}

.teacher-name {
font-size: 1.1rem;
font-weight: 700;
color: white;
text-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
}

/* Cards */
.card {
background: rgba(255, 255, 255, 0.05);
backdrop-filter: blur(30px);
border-radius: 20px;
padding: 30px;
margin-bottom: 25px;
box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1),
inset 0 1px 0 rgba(255, 255, 255, 0.1);
transition: all 0.4s ease;
border: 1px solid rgba(255, 255, 255, 0.1);
position: relative;
overflow: hidden;
}

.card::before {
content: "";
position: absolute;
top: 0;
left: 0;
right: 0;
height: 5px;
background: var(--english-gradient);
}

.card:hover {
transform: translateY(-8px) scale(1.02);
box-shadow: var(--shadow-hover);
}

.section-title {
text-align: center;
color: var(--text);
margin-bottom: 30px;
font-size: 2rem;
font-weight: 800;
position: relative;
padding-bottom: 15px;
}

.section-title::after {
content: "";
position: absolute;
bottom: 0;
left: 50%;
transform: translateX(-50%);
width: 100px;
height: 4px;
background: var(--accent-gradient);
border-radius: 2px;
}

/* Question Design */
.question-box {
background: var(--card-bg);
backdrop-filter: blur(20px);
padding: 30px;
margin-bottom: 25px;
border-radius: 20px;
box-shadow: var(--shadow);
border: 1px solid var(--border);
transition: all 0.4s ease;
position: relative;
overflow: hidden;
}

.question-box::before {
content: "";
position: absolute;
top: 0;
left: 0;
width: 100%;
height: 5px;
background: var(--primary-gradient);
}

.question-box:hover {
transform: translateY(-5px);
box-shadow: var(--shadow-hover);
}

.question-number {
font-size: 1.3em;
color: var(--primary);
margin-bottom: 15px;
font-weight: bold;
display: flex;
align-items: center;
gap: 10px;
}

.question-number i {
color: var(--accent);
font-size: 1.2em;
}

.question-text {
font-size: 1.2em;
margin-bottom: 25px;
line-height: 1.7;
color: var(--text);
font-weight: 500;
}

.options {
position: relative;
}

.options label {
display: flex;
align-items: center;
padding: 18px 20px;
margin: 12px 0;
border: 2px solid var(--border);
border-radius: 15px;
cursor: pointer;
transition: all 0.3s ease;
background: var(--card-bg);
position: relative;
overflow: hidden;
font-weight: 500;
text-align: left;
}

.options label::before {
content: "";
position: absolute;
right: 0;
top: 0;
height: 100%;
width: 0;
background: var(--primary-gradient);
transition: width 0.3s ease;
z-index: 0;
}

.options label:hover:not(.locked) {
border-color: var(--primary);
transform: translateX(-8px);
box-shadow: 0 5px 15px rgba(52, 152, 219, 0.2);
}

.options label:hover:not(.locked)::before {
width: 4px;
}

.options input[type="radio"] {
margin-right: 12px;
transform: scale(1.3);
z-index: 1;
}

.options label.locked {
cursor: not-allowed;
opacity: 0.8;
pointer-events: none;
}

.options input[type="radio"]:disabled {
cursor: not-allowed;
}

.options label.selected {
background: linear-gradient(135deg, rgba(52, 152, 219, 0.15), rgba(46, 204, 113, 0.15));
border: 2px solid var(--accent);
box-shadow: 0 0 15px rgba(46, 204, 113, 0.3);
}

.options label.correct-answer {
background: linear-gradient(135deg, rgba(46, 204, 113, 0.2), rgba(39, 174, 96, 0.2));
border: 2px solid var(--accent);
box-shadow: 0 0 15px rgba(46, 204, 113, 0.3);
animation: correctPulse 0.5s ease;
}

@keyframes correctPulse {
0% { transform: scale(1); }
50% { transform: scale(1.02); }
100% { transform: scale(1); }
}

.options label.correct-answer::before {
width: 6px;
background: var(--accent-gradient);
}

.options label.wrong-answer {
background: linear-gradient(135deg, rgba(231, 76, 60, 0.2), rgba(192, 57, 43, 0.2));
border: 2px solid var(--tertiary);
box-shadow: 0 0 15px rgba(231, 76, 60, 0.3);
animation: wrongShake 0.5s ease;
}

@keyframes wrongShake {
0%, 100% { transform: translateX(0); }
25% { transform: translateX(-5px); }
75% { transform: translateX(5px); }
}

.options label.wrong-answer::before {
width: 6px;
background: var(--tertiary-gradient);
}

.correct {
color: var(--accent);
font-weight: bold;
}

.wrong {
color: var(--tertiary);
font-weight: bold;
}

.explanation {
margin-top: 25px;
padding: 25px;
border-radius: 15px;
display: none;
background: linear-gradient(135deg, rgba(52, 152, 219, 0.05), rgba(46, 204, 113, 0.05));
border-right: 4px solid var(--accent);
animation: slideDown 0.5s ease;
backdrop-filter: blur(10px);
}

@keyframes slideDown {
from {
opacity: 0;
transform: translateY(-15px);
}
to {
opacity: 1;
transform: translateY(0);
}
}

.explanation-line {
padding: 15px;
margin: 10px 0;
border-radius: 10px;
transition: all 0.3s ease;
text-align: left;
}

.explanation-correct {
background: linear-gradient(135deg, rgba(46, 204, 113, 0.1), rgba(39, 174, 96, 0.1));
border-left: 3px solid var(--accent);
}

.explanation-wrong-1 {
background: linear-gradient(135deg, rgba(52, 152, 219, 0.1), rgba(41, 128, 185, 0.1));
border-left: 3px solid var(--primary);
}

.explanation-wrong-2 {
background: linear-gradient(135deg, rgba(155, 89, 182, 0.1), rgba(142, 68, 173, 0.1));
border-left: 3px solid var(--secondary);
}

.explanation-wrong-3 {
background: linear-gradient(135deg, rgba(243, 156, 18, 0.1), rgba(214, 137, 16, 0.1));
border-left: 3px solid var(--quaternary);
}

/* Buttons */
.btn-primary {
background: var(--accent-gradient);
color: white;
box-shadow: var(--glow-accent), 0 8px 25px rgba(46, 204, 113, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
position: relative;
overflow: hidden;
z-index: 1;
transition: all 0.4s ease;
}

.btn-primary::before {
content: '';
position: absolute;
top: 0;
right: -100%;
width: 100%;
height: 100%;
background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
transition: right 0.7s;
z-index: -1;
}

.btn-primary:hover {
transform: translateY(-8px) scale(1.05);
box-shadow: var(--glow-accent), 0 15px 40px rgba(46, 204, 113, 0.6);
border-color: rgba(255, 255, 255, 0.5);
}

.btn-primary:hover::before {
right: 100%;
}

.btn-secondary {
background: var(--primary-gradient);
color: white;
box-shadow: var(--glow-primary), 0 8px 25px rgba(52, 152, 219, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
position: relative;
overflow: hidden;
z-index: 1;
}

.btn-secondary::before {
content: '';
position: absolute;
top: 0;
right: -100%;
width: 100%;
height: 100%;
background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
transition: right 0.7s;
z-index: -1;
}

.btn-secondary:hover {
transform: translateY(-8px) scale(1.05);
box-shadow: var(--glow-primary), 0 15px 40px rgba(52, 152, 219, 0.6);
border-color: rgba(255, 255, 255, 0.5);
}

.btn-secondary:hover::before {
right: 100%;
}

.btn-islamic {
background: var(--english-gradient);
color: white;
box-shadow: var(--glow-english), 0 8px 25px rgba(52, 152, 219, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
animation: english-pulse 2s infinite alternate;
}

@keyframes english-pulse {
0% {
box-shadow: var(--glow-english), 0 8px 25px rgba(52, 152, 219, 0.4);
}
100% {
box-shadow: 0 0 25px rgba(52, 152, 219, 0.8),
0 0 50px rgba(46, 204, 113, 0.6),
0 0 75px rgba(155, 89, 182, 0.4),
0 15px 40px rgba(52, 152, 219, 0.6);
}
}

.btn-success {
background: var(--accent-gradient);
color: white;
box-shadow: var(--glow-accent), 0 8px 25px rgba(46, 204, 113, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
}

.btn-warning {
background: var(--tertiary-gradient);
color: white;
box-shadow: var(--glow-tertiary), 0 8px 25px rgba(231, 76, 60, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
}

/* Navigation Buttons */
.navigation {
display: flex;
justify-content: space-between;
margin-top: 30px;
gap: 20px;
}

.btn {
padding: 15px 30px;
border-radius: 15px;
font-weight: 700;
text-decoration: none;
transition: all 0.3s ease;
display: inline-flex;
align-items: center;
gap: 10px;
font-size: 1rem;
border: none;
cursor: pointer;
position: relative;
overflow: hidden;
}

.btn::before {
content: "";
position: absolute;
top: 0;
right: -100%;
width: 100%;
height: 100%;
background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
transition: right 0.6s;
}

.btn:hover::before {
right: 100%;
}

.btn:disabled {
background: #9CA3AF;
cursor: not-allowed;
transform: none;
box-shadow: none;
opacity: 0.6;
}

.btn:disabled:hover::before {
right: -100%;
}

/* Progress Bar */
.progress-bar {
height: 15px;
background: rgba(255, 255, 255, 0.2);
border-radius: 10px;
margin-bottom: 30px;
overflow: hidden;
box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.1);
position: relative;
backdrop-filter: blur(10px);
}

.progress {
height: 100%;
background: var(--english-gradient);
box-shadow: 0 0 15px rgba(52, 152, 219, 0.5);
width: 0%;
transition: width 0.5s ease;
border-radius: 10px;
position: relative;
overflow: hidden;
}

.progress::after {
content: "";
position: absolute;
top: 0;
right: -100%;
width: 100%;
height: 100%;
background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
animation: shimmer 1.5s infinite;
}

@keyframes shimmer {
0% { right: -100%; }
100% { right: 100%; }
}

/* Results Box */
#result-box {
background: var(--card-bg);
backdrop-filter: blur(20px);
padding: 30px;
margin-top: 30px;
border-radius: 20px;
box-shadow: var(--shadow);
border: 1px solid var(--border);
display: none;
animation: slideUp 0.6s ease;
}

@keyframes slideUp {
from {
opacity: 0;
transform: translateY(30px);
}
to {
opacity: 1;
transform: translateY(0);
}
}

.controls {
display: flex;
justify-content: space-between;
align-items: center;
margin-top: 30px;
flex-wrap: wrap;
gap: 20px;
}

.quiz-info {
font-size: 1rem;
color: var(--light-text);
background: linear-gradient(135deg, rgba(52, 152, 219, 0.1), rgba(46, 204, 113, 0.1));
padding: 10px 20px;
border-radius: 25px;
font-weight: 600;
backdrop-filter: blur(10px);
}

/* Timer */
#timer {
font-size: 1.1rem;
font-weight: bold;
color: white;
margin-left: 20px;
display: flex;
align-items: center;
gap: 8px;
background: rgba(52, 152, 219, 0.2);
backdrop-filter: blur(20px);
padding: 10px 20px;
border-radius: 25px;
border: 2px solid rgba(52, 152, 219, 0.3);
box-shadow: 0 0 15px rgba(52, 152, 219, 0.2);
}

.timer-warning {
background: rgba(231, 76, 60, 0.2) !important;
border-color: rgba(231, 76, 60, 0.3) !important;
box-shadow: 0 0 20px rgba(231, 76, 60, 0.3) !important;
animation: warning-pulse 0.8s infinite alternate;
}

@keyframes warning-pulse {
from {
box-shadow: 0 0 15px rgba(231, 76, 60, 0.3);
}
to {
box-shadow: 0 0 25px rgba(231, 76, 60, 0.5), 0 0 40px rgba(231, 76, 60, 0.3);
}
}

@keyframes pulse {
0% { transform: scale(1); }
50% { transform: scale(1.05); }
100% { transform: scale(1); }
}

/* Dark Theme */
.dark-theme .btn-primary,
.dark-theme .btn-secondary {
border-color: rgba(255, 255, 255, 0.2);
}

.dark-theme .theme-btn,
.dark-theme .back-btn {
background: rgba(52, 152, 219, 0.15);
border-color: rgba(255, 255, 255, 0.2);
}

.dark-theme .card {
background: rgba(15, 30, 45, 0.7);
border-color: rgba(255, 255, 255, 0.05);
}

.dark-theme .hero-section {
background: linear-gradient(135deg, rgba(52, 152, 219, 0.1), rgba(46, 204, 113, 0.1));
border-color: rgba(255, 255, 255, 0.05);
}

/* Responsive */
@media (max-width: 768px) {
body {
padding-top: 70px;
}

.header-container {
padding: 0 15px;
flex-direction: column;
gap: 15px;
}

.title-section h1 {
font-size: 1.3rem;
}

.hero-title {
font-size: 1.8rem;
}

.hero-subtitle {
font-size: 1rem;
}

.card, .question-box {
padding: 25px;
}

.navigation {
flex-direction: column;
gap: 15px;
}

.btn {
width: 100%;
justify-content: center;
padding: 14px 25px;
font-size: 1rem;
}

.theme-btn, .back-btn {
padding: 8px 15px;
font-size: 0.9rem;
}

.controls {
flex-direction: column;
align-items: stretch;
}

.form-row {
flex-direction: column;
}

.student-info-display {
flex-direction: column;
align-items: flex-start;
}

.student-details {
flex-direction: column;
gap: 15px;
}
}

@media (max-width: 480px) {
.header-container {
text-align: center;
}

.header-actions {
justify-content: center;
}

.question-box {
padding: 20px;
}

.options label {
padding: 15px;
}

.hero-section {
padding: 25px;
}

.section-title {
font-size: 1.6rem;
}
}

/* Animations */
.fade-in {
animation: fadeIn 0.8s ease;
}

@keyframes fadeIn {
from {
opacity: 0;
transform: translateY(20px);
}
to {
opacity: 1;
transform: translateY(0);
}
}

.bounce-in {
animation: bounceIn 0.8s ease;
}

@keyframes bounceIn {
0% {
opacity: 0;
transform: scale(0.3);
}
50% {
opacity: 1;
transform: scale(1.05);
}
70% {
transform: scale(0.95);
}
100% {
opacity: 1;
transform: scale(1);
}
}

/* Background Animation */
.bg-animation {
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
z-index: -1;
opacity: 0.3;
}

.floating-shapes {
position: absolute;
width: 100%;
height: 100%;
}

.shape {
position: absolute;
background: var(--english-gradient);
opacity: 0.08;
filter: blur(40px);
border-radius: 50%;
animation: float 6s ease-in-out infinite;
}

.shape:nth-child(1) {
width: 100px;
height: 100px;
top: 10%;
left: 10%;
animation-delay: 0s;
}

.shape:nth-child(2) {
width: 150px;
height: 150px;
top: 60%;
right: 10%;
animation-delay: 2s;
}

.shape:nth-child(3) {
width: 80px;
height: 80px;
bottom: 20%;
left: 20%;
animation-delay: 4s;
}

@keyframes float {
0%, 100% {
transform: translateY(0) rotate(0deg);
}
50% {
transform: translateY(-20px) rotate(180deg);
}
}

/* Charts */
.chart-container {
position: relative;
height: 300px;
margin: 30px 0;
background: var(--card-bg);
border-radius: 15px;
padding: 20px;
}

/* Tips Container */
.tips-container {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
gap: 20px;
margin: 30px 0;
}

.tip-card {
background: var(--card-bg);
border-radius: 15px;
padding: 25px;
transition: all 0.3s ease;
border-left: 5px solid var(--primary);
}

.tip-card:hover {
transform: translateY(-5px);
box-shadow: var(--shadow-hover);
}

.tip-card h4 {
color: var(--primary);
margin-bottom: 15px;
display: flex;
align-items: center;
gap: 10px;
}

/* Modals */
.modal {
display: none;
position: fixed;
z-index: 2000;
left: 0;
top: 0;
width: 100%;
height: 100%;
background-color: rgba(0, 0, 0, 0.7);
backdrop-filter: blur(5px);
animation: fadeIn 0.3s ease;
}

.modal-content {
background: var(--card-bg);
margin: 5% auto;
padding: 30px;
border-radius: 20px;
width: 90%;
max-width: 600px;
max-height: 80vh;
overflow-y: auto;
box-shadow: var(--shadow-hover);
border: 1px solid var(--border);
position: relative;
animation: slideUp 0.5s ease;
}

.close-modal {
position: absolute;
right: 20px;
top: 20px;
color: var(--primary);
font-size: 28px;
font-weight: bold;
cursor: pointer;
width: 40px;
height: 40px;
display: flex;
align-items: center;
justify-content: center;
border-radius: 50%;
background: rgba(52, 152, 219, 0.1);
transition: all 0.3s ease;
}

.close-modal:hover {
background: rgba(52, 152, 219, 0.2);
transform: rotate(90deg);
}

.modal-header {
text-align: center;
margin-bottom: 25px;
padding-bottom: 15px;
border-bottom: 2px solid var(--border);
}

.modal-header h3 {
color: var(--text);
font-size: 1.8rem;
display: flex;
align-items: center;
justify-content: center;
gap: 12px;
}

/* Questions Grid Modal */
#questions-grid-modal {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(60px, 1fr));
gap: 12px;
margin: 25px 0;
}

.question-status-grid-modal {
width: 60px;
height: 60px;
border: 2px solid rgba(52, 152, 219, 0.3);
border-radius: 15px;
display: flex;
align-items: center;
justify-content: center;
cursor: pointer;
font-weight: 700;
transition: all 0.3s ease;
background: var(--card-bg);
position: relative;
overflow: hidden;
font-size: 1.1rem;
}

.question-status-grid-modal::before {
content: "";
position: absolute;
top: 0;
left: 0;
width: 100%;
height: 100%;
background: var(--accent-gradient);
opacity: 0;
transition: opacity 0.3s ease;
}

.question-status-grid-modal:hover:not(.locked) {
transform: translateY(-3px) scale(1.1);
box-shadow: var(--shadow);
}

.question-status-grid-modal.current {
background: var(--accent-gradient);
border-color: rgba(255, 255, 255, 0.5);
box-shadow: var(--glow-accent), 0 5px 15px rgba(46, 204, 113, 0.3);
animation: pulse 2s infinite;
}

.question-status-grid-modal.answered {
background: var(--secondary-gradient);
border-color: rgba(255, 255, 255, 0.5);
box-shadow: var(--glow-secondary), 0 5px 15px rgba(155, 89, 182, 0.3);
}

.question-status-grid-modal.flagged {
background: var(--tertiary-gradient);
border-color: rgba(255, 255, 255, 0.5);
box-shadow: var(--glow-tertiary), 0 5px 15px rgba(231, 76, 60, 0.3);
}

.question-status-grid-modal.locked {
cursor: not-allowed;
opacity: 0.7;
}

.legend-modal {
display: flex;
flex-wrap: wrap;
gap: 20px;
margin: 20px 0;
justify-content: center;
}

.legend-item-modal {
display: flex;
align-items: center;
gap: 10px;
font-size: 0.9rem;
}

/* Score Modal */
.current-score-content {
text-align: center;
padding: 20px;
}

.score-circle {
width: 150px;
height: 150px;
margin: 20px auto;
position: relative;
}

.score-circle svg {
transform: rotate(-90deg);
}

.score-circle circle {
fill: none;
stroke-width: 10;
stroke-linecap: round;
}

.score-bg {
stroke: var(--border);
}

.score-fill {
stroke: var(--accent);
stroke-dasharray: 314;
stroke-dashoffset: 314;
transition: stroke-dashoffset 1s ease;
}

.score-text {
position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);
font-size: 2rem;
font-weight: bold;
color: var(--accent);
}

.score-details {
margin-top: 25px;
font-size: 1.1rem;
line-height: 1.8;
}

.score-details p {
margin: 10px 0;
}

/* Sound Controls */
.sound-controls {
display: flex;
align-items: center;
gap: 10px;
margin-top: 15px;
}

.sound-btn {
background: rgba(255, 255, 255, 0.1);
border: 1px solid rgba(255, 255, 255, 0.2);
border-radius: 50%;
width: 40px;
height: 40px;
display: flex;
align-items: center;
justify-content: center;
cursor: pointer;
color: white;
transition: all 0.3s ease;
}

.sound-btn:hover {
background: rgba(255, 255, 255, 0.2);
transform: scale(1.1);
}

.sound-btn.muted {
opacity: 0.5;
}

.sound-btn.muted i {
color: #ff6b6b;
}

/* Loading Spinner */
.spinner {
border: 4px solid rgba(255, 255, 255, 0.3);
border-radius: 50%;
border-top: 4px solid var(--accent);
width: 40px;
height: 40px;
animation: spin 1s linear infinite;
margin: 20px auto;
}

@keyframes spin {
0% { transform: rotate(0deg); }
100% { transform: rotate(360deg); }
}
</style>
</head>
<body>
<!-- Background Animation -->
<div class="bg-animation">
<div class="floating-shapes">
<div class="shape"></div>
<div class="shape"></div>
<div class="shape"></div>
</div>
</div>

<!-- Header -->
<header class="glass-effect">
<div class="header-container">
<div class="title-section">
<h1>Interactive English Grammar Test</h1>
</div>
<div class="header-actions">
<button class="theme-btn" id="themeBtn">
<i class="fas fa-moon"></i>
</button>
</div>
</div>
</header>

<!-- Main Content -->
<main>
<!-- Hero Section -->
<section class="hero-section glass-effect">
<div class="hero-content">
<h1 class="hero-title">Comparative & Superlative Adjectives</h1>
<p class="hero-subtitle">Test your knowledge of English grammar rules with this interactive quiz</p>
<div class="quiz-info">Questions: 15 | Time: 15 minutes</div>

<!-- Student Info Form -->
<div id="studentInfoForm" class="student-info-form">
<h3><i class="fas fa-user-graduate"></i> Enter Your Information</h3>
<div class="form-row">
<div class="input-group">
<label for="studentName"><i class="fas fa-user"></i> Student Name</label>
<input type="text" id="studentName" placeholder="Enter your full name" value="">
</div>
<div class="input-group">
<label for="studentClass"><i class="fas fa-school"></i> Class/Grade</label>
<input type="text" id="studentClass" placeholder="Enter your class/grade" value="">
</div>
</div>
<button class="btn btn-primary" onclick="saveStudentInfo()" style="width: 100%;">
<i class="fas fa-save"></i> Save Information & Start Test
</button>
</div>

<!-- Student Info Display -->
<div id="studentInfoDisplay" class="student-info-display" style="display: none;">
<div class="student-details">
<div class="student-detail">
<span>Student Name</span>
<span id="displayStudentName"></span>
</div>
<div class="student-detail">
<span>Class/Grade</span>
<span id="displayStudentClass"></span>
</div>
</div>
<button class="edit-student-btn" onclick="editStudentInfo()">
<i class="fas fa-edit"></i> Edit
</button>
</div>

<div class="teacher-info">
<span class="teacher-name">Fahad Al-Khalidi</span>
</div>
<div class="sound-controls">
<button class="sound-btn" id="soundToggleBtn" title="Toggle Sounds">
<i class="fas fa-volume-up"></i>
</button>
<span style="font-size: 0.9rem; opacity: 0.8;">Sounds On</span>
</div>
</div>
</section>

<!-- Progress Bar -->
<div class="progress-bar glass-effect">
<div class="progress" id="progress"></div>
</div>

<!-- Quiz Container -->
<div id="quiz"></div>

<!-- Controls -->
<div class="controls">
<div class="quiz-info" id="quiz-info"></div>
<div id="timer">⏱️ <span id="time-display">15:00</span></div>
<div style="display: flex; gap: 15px; flex-wrap: wrap;">
<button class="btn btn-primary" onclick="openQuestionsModal()">
<i class="fas fa-list"></i>
Questions List
</button>
<button class="btn btn-warning" onclick="toggleMarkForReview()" id="mark-review-btn">
<i class="fas fa-flag"></i>
Mark for Review
</button>
<button class="btn btn-islamic" onclick="finishQuiz()">
<i class="fas fa-flag-checkered"></i>
Finish Test
</button>
<button class="btn btn-secondary" onclick="openCurrentScoreModal()">
<i class="fas fa-chart-bar"></i>
Current Score
</button>
</div>
</div>

<!-- Final Results -->
<div id="result-box" class="card">
<h3 id="result" style="color: var(--text); margin-bottom: 20px;"></h3>
<p id="percentage" style="font-size: 1.4rem; margin-bottom: 15px;"></p>
<p id="evaluation" style="font-weight: bold; font-size: 1.3rem;"></p>

<!-- Advanced Results -->
<div id="advanced-results" style="display: none;">
<div class="chart-container">
<canvas id="performanceChart"></canvas>
</div>

<!-- Tips Section -->
<div class="tips-container" id="tips-container"></div>

<!-- Share Results -->
<div class="share-results">
<h4 style="color: var(--text); margin-bottom: 20px;">
<i class="fas fa-file-pdf"></i> Test Report
</h4>
<div class="share-buttons" style="display: flex; gap: 15px; flex-wrap: wrap;">
<button class="btn btn-success" onclick="generatePDF()">
<i class="fas fa-file-pdf"></i> Download PDF Report
</button>
<button class="btn btn-primary" onclick="shareToWhatsApp()">
<i class="fab fa-whatsapp"></i> Share via WhatsApp
</button>
<button class="btn btn-secondary" onclick="restartQuiz()">
<i class="fas fa-redo"></i> Restart Test
</button>
</div>
</div>
</div>
</div>
</main>

<!-- Current Score Modal -->
<div id="currentScoreModal" class="modal">
<div class="modal-content">
<span class="close-modal" onclick="closeCurrentScoreModal()">&times;</span>
<div class="modal-header">
<h3><i class="fas fa-chart-bar"></i> Current Score</h3>
</div>
<div class="current-score-content">
<div class="score-circle">
<svg width="150" height="150">
<circle class="score-bg" cx="75" cy="75" r="70"></circle>
<circle class="score-fill" cx="75" cy="75" r="70" id="score-circle-fill"></circle>
</svg>
<div class="score-text" id="score-percentage">0%</div>
</div>
<div class="score-details">
<p id="current-score-details"></p>
<p id="current-correct-details"></p>
<p id="current-progress-details"></p>
</div>
</div>
</div>
</div>

<!-- Questions List Modal -->
<div id="questionsModal" class="modal">
<div class="modal-content">
<span class="close-modal" onclick="closeQuestionsModal()">&times;</span>
<div class="modal-header">
<h3><i class="fas fa-th-list"></i> Questions List</h3>
</div>
<div id="questions-grid-modal"></div>
<div class="legend-modal">
<div class="legend-item-modal">
<div class="question-status-grid-modal" style="background: var(--accent-gradient); color: white;"></div>
<span>Current Question</span>
</div>
<div class="legend-item-modal">
<div class="question-status-grid-modal" style="background: var(--secondary-gradient); color: white;"></div>
<span>Answered</span>
</div>
<div class="legend-item-modal">
<div class="question-status-grid-modal" style="background: var(--tertiary-gradient); color: var(--text);"></div>
<span>Marked for Review</span>
</div>
<div class="legend-item-modal">
<div class="question-status-grid-modal" style="background: var(--card-bg); border-color: var(--border);"></div>
<span>Not Answered</span>
</div>
</div>
<button class="btn btn-primary" onclick="closeQuestionsModal()" style="margin-top:20px; width: 100%;">
<i class="fas fa-times"></i>
Close List
</button>
</div>
</div>

<script>
// Questions Array - Comparative and Superlative Adjectives
const questions = [
{
"id": 1,
"q": "1️⃣ Buses are ______ than taxis.",
"options": [
"A) cheap",
"B) cheaper",
"C) cheapest",
"D) more cheap"
],
"answer": 1,
"explanations": {
"correct": "Correct! 'Cheaper' is the comparative form of 'cheap' (add -er for short adjectives).",
"wrong1": "A) cheap - This is the base form, not comparative.",
"wrong2": "C) cheapest - This is superlative, used for comparing three or more things.",
"wrong3": "D) more cheap - 'Cheap' is a short adjective, so we add -er, not 'more'."
}
},
{
"id": 2,
"q": "2️⃣ Planes are ______ means of transport.",
"options": [
"A) faster",
"B) fast",
"C) fastest",
"D) more fast"
],
"answer": 0,
"explanations": {
"correct": "Correct! 'Faster' is the comparative form (fast → faster → fastest).",
"wrong1": "B) fast - This is the base form, not comparative.",
"wrong2": "C) fastest - This is superlative, used when comparing three or more.",
"wrong3": "D) more fast - Irregular adjective: fast → faster, not 'more fast'."
}
},
{
"id": 3,
"q": "3️⃣ Trains are ______ than buses.",
"options": [
"A) fast",
"B) faster",
"C) fastest",
"D) more fast"
],
"answer": 1,
"explanations": {
"correct": "Correct! Use comparative form 'faster' when comparing two things.",
"wrong1": "A) fast - Base form, not comparative.",
"wrong2": "C) fastest - Superlative form, not comparative.",
"wrong3": "D) more fast - Incorrect form for this adjective."
}
},
{
"id": 4,
"q": "4️⃣ The subway is ______ way to travel.",
"options": [
"A) less expensive",
"B) cheaper",
"C) the least expensive",
"D) most expensive"
],
"answer": 2,
"explanations": {
"correct": "Correct! 'The least expensive' is the superlative form for negative comparison.",
"wrong1": "A) less expensive - This is comparative, not superlative.",
"wrong2": "B) cheaper - This means the same but uses different adjective.",
"wrong3": "D) most expensive - Opposite meaning of what's likely intended."
}
},
{
"id": 5,
"q": "5️⃣ A plane ticket is ______ than a bus ticket.",
"options": [
"A) expensive",
"B) most expensive",
"C) more expensive",
"D) expensiver"
],
"answer": 2,
"explanations": {
"correct": "Correct! For adjectives with 3+ syllables, use 'more' + adjective.",
"wrong1": "A) expensive - Base form, not comparative.",
"wrong2": "B) most expensive - Superlative form, not comparative.",
"wrong3": "D) expensiver - Long adjectives don't take -er ending."
}
},
{
"id": 6,
"q": "6️⃣ This exercise is ______ than the last one.",
"options": [
"A) easy",
"B) easier",
"C) easiest",
"D) more easy"
],
"answer": 1,
"explanations": {
"correct": "Correct! Easy → easier (change y to i and add -er).",
"wrong1": "A) easy - Base form, not comparative.",
"wrong2": "C) easiest - Superlative form, not comparative.",
"wrong3": "D) more easy - Irregular: easy → easier, not 'more easy'."
}
},
{
"id": 7,
"q": "7️⃣ This is the ______ movie I have ever seen.",
"options": [
"A) bad",
"B) worse",
"C) worst",
"D) badly"
],
"answer": 2,
"explanations": {
"correct": "Correct! Bad → worse (comparative) → worst (superlative).",
"wrong1": "A) bad - Base form, not superlative.",
"wrong2": "B) worse - This is comparative, not superlative.",
"wrong3": "D) badly - This is an adverb, not an adjective."
}
},
{
"id": 8,
"q": "8️⃣ My house is ______ as yours.",
"options": [
"A) big",
"B) same",
"C) as big",
"D) bigger"
],
"answer": 2,
"explanations": {
"correct": "Correct! 'As big as' is the correct form for equality comparison.",
"wrong1": "A) big - Missing 'as...as' structure.",
"wrong2": "B) same - Should be 'the same size as'.",
"wrong3": "D) bigger - This is comparative, not equality comparison."
}
},
{
"id": 9,
"q": "9️⃣ Today is ______ than yesterday.",
"options": [
"A) hot",
"B) hotter",
"C) hottest",
"D) more hot"
],
"answer": 1,
"explanations": {
"correct": "Correct! Hot → hotter (double the consonant and add -er).",
"wrong1": "A) hot - Base form, not comparative.",
"wrong2": "C) hottest - Superlative form, not comparative.",
"wrong3": "D) more hot - Short adjective, use -er ending."
}
},
{
"id": 10,
"q": "🔟 This is the ______ exam of the year.",
"options": [
"A) difficult",
"B) more difficult",
"C) most difficult",
"D) difficulty"
],
"answer": 2,
"explanations": {
"correct": "Correct! For long adjectives (3+ syllables), use 'most' + adjective.",
"wrong1": "A) difficult - Base form, not superlative.",
"wrong2": "B) more difficult - Comparative form, not superlative.",
"wrong3": "D) difficulty - This is a noun, not an adjective."
}
},
{
"id": 11,
"q": "1️⃣1️⃣ My English is ______ than before.",
"options": [
"A) good",
"B) better",
"C) best",
"D) more good"
],
"answer": 1,
"explanations": {
"correct": "Correct! Good → better (comparative) → best (superlative).",
"wrong1": "A) good - Base form, not comparative.",
"wrong2": "C) best - Superlative form, not comparative.",
"wrong3": "D) more good - Irregular adjective, doesn't use 'more'."
}
},
{
"id": 12,
"q": "1️⃣2️⃣ That was the ______ day of my life.",
"options": [
"A) happy",
"B) happier",
"C) happiest",
"D) more happy"
],
"answer": 2,
"explanations": {
"correct": "Correct! Happy → happier → happiest (change y to i and add -est).",
"wrong1": "A) happy - Base form, not superlative.",
"wrong2": "B) happier - Comparative form, not superlative.",
"wrong3": "D) more happy - Short adjective, use -er/-est endings."
}
},
{
"id": 13,
"q": "1️⃣3️⃣ A car is ______ than a bicycle.",
"options": [
"A) fast",
"B) faster",
"C) fastest",
"D) most fast"
],
"answer": 1,
"explanations": {
"correct": "Correct! Faster is the comparative form for comparing two things.",
"wrong1": "A) fast - Base form, not comparative.",
"wrong2": "C) fastest - Superlative form, not comparative.",
"wrong3": "D) most fast - Incorrect form for this adjective."
}
},
{
"id": 14,
"q": "1️⃣4️⃣ This phone is ______ than my old one.",
"options": [
"A) modern",
"B) most modern",
"C) more modern",
"D) modernest"
],
"answer": 2,
"explanations": {
"correct": "Correct! For 2-syllable adjectives ending in -n, use 'more' + adjective.",
"wrong1": "A) modern - Base form, not comparative.",
"wrong2": "B) most modern - Superlative form, not comparative.",
"wrong3": "D) modernest - Modern doesn't take -est ending."
}
},
{
"id": 15,
"q": "1️⃣5️⃣ This is ______ hotel in the city.",
"options": [
"A) better",
"B) good",
"C) best",
"D) more good"
],
"answer": 2,
"explanations": {
"correct": "Correct! Good → better → best. Use 'best' for superlative (comparing all hotels).",
"wrong1": "A) better - Comparative form, not superlative.",
"wrong2": "B) good - Base form, not superlative.",
"wrong3": "D) more good - Incorrect form for this irregular adjective."
}
}
];

// Game State Variables
let currentQuestionIndex = 0;
let userAnswers = Array(questions.length).fill(null);
let timeLeft = 15 * 60; // 15 minutes for the test
let timerInterval;
let markedQuestions = [];
let answerLocked = Array(questions.length).fill(false);
let performanceHistory = [];
let shuffledQuestions = [];
let soundEnabled = true;
let studentName = "";
let studentClass = "";
let testStarted = false;

// Audio Elements
const audioElements = {
    correct: new Audio("https://media.vocaroo.com/mp3/19lcrilHKuHR"),
    wrong: new Audio("https://media.vocaroo.com/mp3/1ooZTr9sHVXS"),
    click: null,
    hover: null
};

// Initialize Sounds
function initSounds() {
    // Create simple tones for click and hover
    audioElements.click = new Audio();
    audioElements.hover = new Audio();
    
    // Preload the external audio files
    audioElements.correct.load();
    audioElements.wrong.load();
    
    // Generate simple tones for click and hover
    const audioContext = new (window.AudioContext || window.webkitAudioContext)();
    
    // Click sound (short beep)
    const clickOscillator = audioContext.createOscillator();
    const clickGain = audioContext.createGain();
    clickOscillator.connect(clickGain);
    clickGain.connect(audioContext.destination);
    clickOscillator.frequency.value = 800;
    clickOscillator.type = 'sine';
    clickGain.gain.setValueAtTime(0, audioContext.currentTime);
    clickGain.gain.linearRampToValueAtTime(0.1, audioContext.currentTime + 0.01);
    clickGain.gain.exponentialRampToValueAtTime(0.001, audioContext.currentTime + 0.1);
    clickOscillator.start();
    clickOscillator.stop(audioContext.currentTime + 0.1);
    
    // Hover sound (very short beep)
    const hoverOscillator = audioContext.createOscillator();
    const hoverGain = audioContext.createGain();
    hoverOscillator.connect(hoverGain);
    hoverGain.connect(audioContext.destination);
    hoverOscillator.frequency.value = 600;
    hoverOscillator.type = 'sine';
    hoverGain.gain.setValueAtTime(0, audioContext.currentTime);
    hoverGain.gain.linearRampToValueAtTime(0.05, audioContext.currentTime + 0.01);
    hoverGain.gain.exponentialRampToValueAtTime(0.001, audioContext.currentTime + 0.05);
    hoverOscillator.start();
    hoverOscillator.stop(audioContext.currentTime + 0.05);
}

// Play Sound Function
function playSound(soundName) {
    if (!soundEnabled || !audioElements[soundName]) return;
    
    try {
        // Reset audio to start
        audioElements[soundName].currentTime = 0;
        audioElements[soundName].play().catch(e => {
            console.log("Audio play failed:", e);
        });
    } catch (error) {
        console.log("Sound play error:", error);
    }
}

// Shuffle Options
function shuffleOptions(question) {
    const options = [...question.options];
    const answer = question.answer;
    
    const shuffledIndices = [...Array(options.length).keys()];
    for (let i = shuffledIndices.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [shuffledIndices[i], shuffledIndices[j]] = [shuffledIndices[j], shuffledIndices[i]];
    }
    
    const shuffledOptions = shuffledIndices.map(idx => options[idx]);
    const newAnswer = shuffledIndices.indexOf(answer);
    
    return {
        ...question,
        options: shuffledOptions,
        answer: newAnswer
    };
}

// Load Student Info
function loadStudentInfo() {
    const savedName = localStorage.getItem('englishGrammarStudentName');
    const savedClass = localStorage.getItem('englishGrammarStudentClass');
    
    if (savedName && savedClass) {
        studentName = savedName;
        studentClass = savedClass;
        
        document.getElementById('displayStudentName').textContent = studentName;
        document.getElementById('displayStudentClass').textContent = studentClass;
        
        document.getElementById('studentInfoForm').style.display = 'none';
        document.getElementById('studentInfoDisplay').style.display = 'flex';
        
        return true;
    }
    return false;
}

// Save Student Info
function saveStudentInfo() {
    const nameInput = document.getElementById('studentName');
    const classInput = document.getElementById('studentClass');
    
    studentName = nameInput.value.trim();
    studentClass = classInput.value.trim();
    
    if (!studentName || !studentClass) {
        alert("Please enter both your name and class/grade");
        return;
    }
    
    localStorage.setItem('englishGrammarStudentName', studentName);
    localStorage.setItem('englishGrammarStudentClass', studentClass);
    
    document.getElementById('displayStudentName').textContent = studentName;
    document.getElementById('displayStudentClass').textContent = studentClass;
    
    document.getElementById('studentInfoForm').style.display = 'none';
    document.getElementById('studentInfoDisplay').style.display = 'flex';
    
    // Start the quiz automatically
    if (!testStarted) {
        testStarted = true;
        startTest();
    }
}

// Edit Student Info
function editStudentInfo() {
    document.getElementById('studentName').value = studentName;
    document.getElementById('studentClass').value = studentClass;
    
    document.getElementById('studentInfoForm').style.display = 'block';
    document.getElementById('studentInfoDisplay').style.display = 'none';
}

// Start Test
function startTest() {
    if (!studentName || !studentClass) {
        alert("Please enter your information first");
        return;
    }
    
    testStarted = true;
    
    // Hide student info display
    document.getElementById('studentInfoDisplay').style.display = 'none';
    
    // Load quiz
    loadQuiz();
    startTimer();
    
    // Scroll to quiz
    document.querySelector('#quiz').scrollIntoView({ behavior: 'smooth' });
}

// Load Performance History
function loadPerformanceHistory() {
    const savedHistory = localStorage.getItem('englishGrammarPerformanceHistory');
    if (savedHistory) {
        try {
            performanceHistory = JSON.parse(savedHistory);
        } catch (e) {
            performanceHistory = [];
        }
    }
}

// Save Performance History
function savePerformanceHistory() {
    localStorage.setItem('englishGrammarPerformanceHistory', JSON.stringify(performanceHistory));
}

// Theme Toggle
document.getElementById('themeBtn').addEventListener('click', function() {
    playSound('click');
    document.body.classList.toggle('dark-theme');
    const icon = this.querySelector('i');
    if (document.body.classList.contains('dark-theme')) {
        icon.classList.remove('fa-moon');
        icon.classList.add('fa-sun');
        localStorage.setItem('darkMode', 'enabled');
    } else {
        icon.classList.remove('fa-sun');
        icon.classList.add('fa-moon');
        localStorage.setItem('darkMode', 'disabled');
    }
});

// Check Dark Mode Preference
function checkDarkModePreference() {
    const darkMode = localStorage.getItem('darkMode');
    const icon = document.querySelector('#themeBtn i');

    if (darkMode === 'enabled') {
        document.body.classList.add('dark-theme');
        icon.classList.remove('fa-moon');
        icon.classList.add('fa-sun');
    } else {
        document.body.classList.remove('dark-theme');
        icon.classList.remove('fa-sun');
        icon.classList.add('fa-moon');
    }
}

// Sound Toggle
document.getElementById('soundToggleBtn').addEventListener('click', function() {
    soundEnabled = !soundEnabled;
    const icon = this.querySelector('i');
    const statusText = this.nextElementSibling;
    
    if (soundEnabled) {
        icon.classList.remove('fa-volume-mute');
        icon.classList.add('fa-volume-up');
        this.classList.remove('muted');
        statusText.textContent = 'Sounds On';
        playSound('click');
    } else {
        icon.classList.remove('fa-volume-up');
        icon.classList.add('fa-volume-mute');
        this.classList.add('muted');
        statusText.textContent = 'Sounds Off';
    }
    
    localStorage.setItem('soundEnabled', soundEnabled);
});

// Timer Functions
function startTimer() {
    timerInterval = setInterval(() => {
        timeLeft--;
        updateTimerDisplay();

        if (timeLeft === 5 * 60) {
            playSound('click');
        }
        
        if (timeLeft < 5 * 60 && timeLeft % 60 === 0) {
            playSound('click');
        }

        if (timeLeft <= 0) {
            clearInterval(timerInterval);
            playSound('click');
            finishQuiz();
        }
    }, 1000);
}

function updateTimerDisplay() {
    const minutes = Math.floor(timeLeft / 60);
    const seconds = timeLeft % 60;
    const timeDisplay = document.getElementById('time-display');
    timeDisplay.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;

    if (timeLeft < 300) {
        timeDisplay.classList.add('timer-warning');
    } else {
        timeDisplay.classList.remove('timer-warning');
    }
}

// Modal Functions
function openCurrentScoreModal() {
    playSound('click');
    const score = calculateScore();
    const answeredCount = userAnswers.filter(answer => answer !== null).length;
    const totalQuestions = questions.length;
    const percentage = totalQuestions > 0 ? ((score.correct / totalQuestions) * 100).toFixed(2) : 0;
    
    const circle = document.getElementById('score-circle-fill');
    const text = document.getElementById('score-percentage');
    const circumference = 440;
    const offset = circumference - (percentage / 100) * circumference;
    
    circle.style.strokeDashoffset = offset;
    text.textContent = `${percentage}%`;
    
    document.getElementById('current-score-details').innerHTML = 
        `<strong>Current Score:</strong> ${score.correct} out of ${totalQuestions}`;
    document.getElementById('current-correct-details').innerHTML = 
        `<strong>Correct Answers:</strong> ${score.correct}`;
    document.getElementById('current-progress-details').innerHTML = 
        `<strong>Progress:</strong> ${answeredCount} of ${totalQuestions} (${Math.round((answeredCount/totalQuestions)*100)}%)`;
    
    document.getElementById('currentScoreModal').style.display = 'block';
}

function closeCurrentScoreModal() {
    playSound('click');
    document.getElementById('currentScoreModal').style.display = 'none';
}

function openQuestionsModal() {
    playSound('click');
    const grid = document.getElementById('questions-grid-modal');
    grid.innerHTML = '';

    questions.forEach((_, index) => {
        const btn = document.createElement('div');
        btn.className = `question-status-grid-modal ${index === currentQuestionIndex ? 'current' : ''} ${userAnswers[index] !== null ? 'answered' : ''} ${markedQuestions.includes(index) ? 'flagged' : ''}`;
        btn.innerHTML = `<span>${index + 1}</span>`;
        btn.onclick = () => {
            playSound('click');
            currentQuestionIndex = index;
            loadQuiz();
            closeQuestionsModal();
        };
        grid.appendChild(btn);
    });

    document.getElementById('questionsModal').style.display = 'block';
}

function closeQuestionsModal() {
    playSound('click');
    document.getElementById('questionsModal').style.display = 'none';
}

function toggleMarkForReview() {
    playSound('click');
    const index = markedQuestions.indexOf(currentQuestionIndex);
    const btn = document.getElementById('mark-review-btn');

    if (index === -1) {
        markedQuestions.push(currentQuestionIndex);
        btn.innerHTML = '<i class="fas fa-flag"></i> Remove Mark';
        btn.style.background = 'var(--tertiary-gradient)';
    } else {
        markedQuestions.splice(index, 1);
        btn.innerHTML = '<i class="fas fa-flag"></i> Mark for Review';
        btn.style.background = 'var(--secondary-gradient)';
    }
}

// Load Quiz
function loadQuiz() {
    if (!testStarted && studentName && studentClass) {
        testStarted = true;
    }
    
    const quizDiv = document.getElementById("quiz");

    if (shuffledQuestions.length === 0) {
        shuffledQuestions = questions.map(q => shuffleOptions(q));
    }
    
    const question = shuffledQuestions[currentQuestionIndex];
    const isLocked = answerLocked[currentQuestionIndex];

    let html = `
    <div class="question-box fade-in">
        <div class="question-number">
            <i class="fas fa-question-circle"></i>
            Question ${currentQuestionIndex + 1} of ${questions.length}
            ${isLocked ? '<span style="color: var(--accent); margin-left: 10px;"><i class="fas fa-lock"></i> Locked</span>' : ''}
            ${markedQuestions.includes(currentQuestionIndex) ? '<span style="background: var(--tertiary-gradient); color: white; padding: 5px 10px; border-radius: 10px; font-size: 0.8rem; margin-left: 10px;"><i class="fas fa-flag"></i> Marked</span>' : ''}
        </div>
        <div class="question-text">${question.q}</div>
        <div class="options">
    `;

    question.options.forEach((opt, i) => {
        const isChecked = userAnswers[currentQuestionIndex] === i;
        const isDisabled = isLocked;
        let labelClass = '';

        if (isLocked) {
            labelClass = 'locked';
            if (isChecked) {
                labelClass += userAnswers[currentQuestionIndex] === question.answer ? ' correct-answer' : ' wrong-answer';
            } else if (i === question.answer) {
                labelClass += ' correct-answer';
            }
        } else if (isChecked) {
            labelClass = 'selected';
        }

        html += `
        <label class="${labelClass}">
            <input type="radio" name="q${currentQuestionIndex}" value="${i}" ${isChecked ? 'checked' : ''} ${isDisabled ? 'disabled' : ''} onchange="selectAnswer(${i})" ${isLocked ? 'onclick="return false;"' : ''}>
            ${opt}
            ${isLocked && i === question.answer ? ' <i class="fas fa-check" style="color: var(--accent); margin-left: 5px;"></i>' : ''}
        </label>
        `;
    });

    html += `
        </div>
        <div id="explanation" class="explanation"></div>
    </div>
    <div class="navigation">
        <button class="btn btn-secondary" onclick="previousQuestion()" ${currentQuestionIndex === 0 ? 'disabled' : ''}>
            <i class="fas fa-arrow-left"></i>
            Previous
        </button>
        <button class="btn btn-primary" onclick="nextQuestion()" ${currentQuestionIndex === questions.length - 1 ? 'disabled' : ''}>
            Next
            <i class="fas fa-arrow-right"></i>
        </button>
    </div>
    `;

    quizDiv.innerHTML = html;

    const progress = document.getElementById('progress');
    progress.style.width = questions.length > 0 ? `${((currentQuestionIndex + 1) / questions.length) * 100}%` : '0%';

    document.getElementById('quiz-info').innerHTML = `Question ${currentQuestionIndex + 1} of ${questions.length}`;

    const markBtn = document.getElementById('mark-review-btn');
    if (markedQuestions.includes(currentQuestionIndex)) {
        markBtn.innerHTML = '<i class="fas fa-flag"></i> Remove Mark';
        markBtn.style.background = 'var(--tertiary-gradient)';
    } else {
        markBtn.innerHTML = '<i class="fas fa-flag"></i> Mark for Review';
        markBtn.style.background = 'var(--secondary-gradient)';
    }

    if (userAnswers[currentQuestionIndex] !== null) {
        showExplanation();
    }
}

// Select Answer
function selectAnswer(answerIndex) {
    if (answerLocked[currentQuestionIndex]) {
        return;
    }

    playSound('click');
    
    userAnswers[currentQuestionIndex] = answerIndex;
    answerLocked[currentQuestionIndex] = true;

    const question = shuffledQuestions[currentQuestionIndex];
    if (answerIndex === question.answer) {
        playSound('correct');
    } else {
        playSound('wrong');
    }

    const radioInputs = document.querySelectorAll(`input[name="q${currentQuestionIndex}"]`);
    radioInputs.forEach(input => {
        input.disabled = true;
    });

    const labels = document.querySelectorAll(`input[name="q${currentQuestionIndex}"]`);
    labels.forEach(input => {
        input.closest('label').classList.add('locked');
    });

    showExplanation();
}

// Show Explanation
function showExplanation() {
    const question = shuffledQuestions[currentQuestionIndex];
    const explanationDiv = document.getElementById("explanation");
    const userAnswer = userAnswers[currentQuestionIndex];

    if (userAnswer !== null) {
        explanationDiv.style.display = "block";

        let resultHTML = "";

        if (userAnswer === question.answer) {
            resultHTML = `<p class="correct"><i class="fas fa-check-circle"></i> Correct Answer! Well done!</p>`;
        } else {
            resultHTML = `
            <p class="wrong"><i class="fas fa-times-circle"></i> Incorrect Answer — Correct Answer: <span class="correct">${question.options[question.answer]}</span></p>
            `;
        }

        resultHTML += `
        <div class="explanation-line explanation-correct"><strong>📚 Correct Explanation:</strong> ${questions[currentQuestionIndex].explanations.correct}</div>
        `;

        const wrongKeys = ['wrong1', 'wrong2', 'wrong3'];

        wrongKeys.forEach((key, index) => {
            if (questions[currentQuestionIndex].explanations[key]) {
                resultHTML += `<div class="explanation-line explanation-wrong-${index + 1}"><strong>💡 Note:</strong> ${questions[currentQuestionIndex].explanations[key]}</div>`;
            }
        });

        explanationDiv.innerHTML = resultHTML;
    }
}

// Navigation
function nextQuestion() {
    playSound('click');
    if (currentQuestionIndex < questions.length - 1) {
        currentQuestionIndex++;
        loadQuiz();
    }
}

function previousQuestion() {
    playSound('click');
    if (currentQuestionIndex > 0) {
        currentQuestionIndex--;
        loadQuiz();
    }
}

// Calculate Score
function calculateScore() {
    let totalCorrect = 0;
    userAnswers.forEach((answer, index) => {
        if (answer === questions[index]?.answer) {
            totalCorrect++;
        }
    });

    const total = questions.length;
    const percentage = total > 0 ? ((totalCorrect / total) * 100).toFixed(2) : 0;

    let evaluation = "";
    let evaluationIcon = "";
    if (percentage >= 90) {
        evaluation = "Excellent - Perfect understanding of grammar rules";
        evaluationIcon = "🌟";
    } else if (percentage >= 80) {
        evaluation = "Very Good - Strong grasp of comparatives and superlatives";
        evaluationIcon = "🔵";
    } else if (percentage >= 70) {
        evaluation = "Good - Solid understanding with minor improvements needed";
        evaluationIcon = "🟢";
    } else if (percentage >= 60) {
        evaluation = "Satisfactory - Review needed for some concepts";
        evaluationIcon = "🟡";
    } else {
        evaluation = "Needs Improvement - Review grammar rules thoroughly";
        evaluationIcon = "⚠️";
    }

    return {
        correct: totalCorrect,
        total: total,
        percentage: parseFloat(percentage),
        evaluation: evaluation,
        evaluationIcon: evaluationIcon
    };
}

// Create Performance Chart
function createPerformanceChart() {
    loadPerformanceHistory();
    const ctx = document.getElementById('performanceChart').getContext('2d');
    const dates = performanceHistory.map(attempt => {
        const date = new Date(attempt.date);
        return `${date.getDate()}/${date.getMonth() + 1}`;
    });
    const scores = performanceHistory.map(attempt => attempt.percentage);

    const currentScore = calculateScore().percentage;
    dates.push("Now");
    scores.push(currentScore);

    if (window.performanceChartInstance) {
        window.performanceChartInstance.destroy();
    }

    window.performanceChartInstance = new Chart(ctx, {
        type: 'line',
        data: {
            labels: dates,
            datasets: [{
                label: 'Percentage %',
                data: scores,
                borderColor: 'rgba(52, 152, 219, 1)',
                backgroundColor: 'rgba(52, 152, 219, 0.1)',
                borderWidth: 3,
                fill: true,
                tension: 0.4
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
                legend: {
                    display: true,
                    position: 'top',
                    labels: {
                        color: 'var(--text)',
                        font: {
                            family: 'Tajawal',
                            size: 14
                        }
                    }
                }
            },
            scales: {
                y: {
                    beginAtZero: true,
                    max: 100,
                    ticks: {
                        color: 'var(--text)',
                        callback: function(value) {
                            return value + '%';
                        },
                        font: {
                            family: 'Tajawal',
                            size: 12
                        }
                    },
                    grid: {
                        color: 'rgba(255, 255, 255, 0.1)'
                    }
                },
                x: {
                    ticks: {
                        color: 'var(--text)',
                        font: {
                            family: 'Tajawal',
                            size: 12
                        }
                    },
                    grid: {
                        color: 'rgba(255, 255, 255, 0.1)'
                    }
                }
            }
        }
    });
}

// Create Custom Tips
function createCustomTips() {
    const score = calculateScore();
    const tipsContainer = document.getElementById('tips-container');
    let tipsHTML = '';

    if (score.percentage >= 90) {
        tipsHTML = `
        <div class="tip-card">
            <h4><i class="fas fa-star"></i> Excellent Performance!</h4>
            <p>You have excellent understanding of comparative and superlative adjectives! Keep practicing to maintain this level.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-lightbulb"></i> Advanced Tips</h4>
            <p>Now try learning irregular comparatives like: good/better/best, bad/worse/worst, far/farther(further)/farthest(furthest).</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-book"></i> Next Steps</h4>
            <p>Move on to more advanced grammar topics like conditionals, passive voice, or reported speech.</p>
        </div>
        `;
    } else if (score.percentage >= 70) {
        tipsHTML = `
        <div class="tip-card">
            <h4><i class="fas fa-check-circle"></i> Good Performance</h4>
            <p>You have a good understanding. Focus on: 1-syllable adjectives (-er/-est), 2+ syllable adjectives (more/most), irregular forms.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-book-open"></i> Focus Areas</h4>
            <p>Review: When to use "more" vs "-er", when to double consonants (big → bigger), and irregular forms.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-clock"></i> Practice Strategy</h4>
            <p>Practice with real sentences: "This book is ___ than that one." "She is the ___ student in class."</p>
        </div>
        `;
    } else {
        tipsHTML = `
        <div class="tip-card">
            <h4><i class="fas fa-exclamation-triangle"></i> Needs Improvement</h4>
            <p>Review basic rules: Short adjectives (-er/-est), long adjectives (more/most), and irregular forms.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-graduation-cap"></i> Basic Rules</h4>
            <p>1. One syllable: add -er/-est (fast → faster → fastest)<br>
               2. Two+ syllables: use more/most (beautiful → more beautiful → most beautiful)<br>
               3. Irregular: good → better → best, bad → worse → worst</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-redo"></i> Practice Regularly</h4>
            <p>Take this test again after studying. Focus on understanding why each answer is correct.</p>
        </div>
        `;
    }

    tipsContainer.innerHTML = tipsHTML;
}

// Save Performance Record
function savePerformanceRecord() {
    const score = calculateScore();
    performanceHistory.push({
        date: new Date().toISOString(),
        studentName: studentName,
        studentClass: studentClass,
        score: score.correct,
        total: score.total,
        percentage: score.percentage
    });

    if (performanceHistory.length > 10) {
        performanceHistory = performanceHistory.slice(-10);
    }

    savePerformanceHistory();
}

// Generate PDF Report
function generatePDF() {
    playSound('click');
    
    // Show loading message
    const shareButtons = document.querySelector('.share-buttons');
    const originalHTML = shareButtons.innerHTML;
    shareButtons.innerHTML = '<div class="spinner"></div><p>Generating PDF report...</p>';
    
    setTimeout(() => {
        const score = calculateScore();
        const answeredCount = userAnswers.filter(answer => answer !== null).length;
        const timeSpent = 15 - (timeLeft / 60);
        
        const { jsPDF } = window.jspdf;
        const doc = new jsPDF();
        
        // Add English fonts
        doc.setFont('helvetica');
        
        // Title
        doc.setFontSize(24);
        doc.setTextColor(52, 152, 219);
        doc.text('English Grammar Test Report', 105, 20, null, null, 'center');
        
        doc.setFontSize(16);
        doc.setTextColor(46, 204, 113);
        doc.text('Topic: Comparative & Superlative Adjectives', 105, 30, null, null, 'center');
        
        doc.setFontSize(12);
        doc.setTextColor(100, 100, 100);
        doc.text(`Test Date: ${new Date().toLocaleDateString('en-US')}`, 105, 40, null, null, 'center');
        doc.text(`Teacher: Fahad Al-Khalidi`, 105, 47, null, null, 'center');
        
        // Student Information
        doc.setFontSize(14);
        doc.setTextColor(30, 30, 30);
        doc.text('Student Information:', 20, 65);
        doc.setFontSize(12);
        doc.text(`Name: ${studentName}`, 20, 75);
        doc.text(`Class/Grade: ${studentClass}`, 20, 82);
        
        // Line separator
        doc.setDrawColor(52, 152, 219);
        doc.setLineWidth(0.5);
        doc.line(20, 90, 190, 90);
        
        // Main Results
        doc.setFontSize(18);
        doc.setTextColor(30, 30, 30);
        doc.text('Test Results', 20, 105);
        
        doc.setFontSize(14);
        doc.text(`Final Score: ${score.correct} out of ${score.total}`, 20, 120);
        doc.text(`Percentage: ${score.percentage}%`, 20, 130);
        doc.text(`Evaluation: ${score.evaluation}`, 20, 140);
        doc.text(`Questions Answered: ${answeredCount} of ${questions.length}`, 20, 150);
        doc.text(`Time Spent: ${timeSpent.toFixed(2)} minutes of 15 minutes`, 20, 160);
        
        // Performance Graph Placeholder
        doc.setFontSize(16);
        doc.text('Performance History:', 20, 180);
        doc.setFontSize(12);
        doc.text('Your performance graph is available in the online report.', 20, 190);
        
        // Question Details (New Page)
        doc.addPage();
        doc.setFontSize(18);
        doc.text('Question Details', 20, 20);
        
        doc.setFontSize(12);
        let yPos = 35;
        
        for (let i = 0; i < questions.length; i++) {
            if (yPos > 270) {
                doc.addPage();
                yPos = 20;
                doc.setFontSize(12);
            }
            
            const status = userAnswers[i] === null ? 'Not Answered' : 
                          (userAnswers[i] === questions[i].answer ? 'Correct' : 'Incorrect');
            const statusColor = userAnswers[i] === null ? [150, 150, 150] : 
                               (userAnswers[i] === questions[i].answer ? [46, 204, 113] : [231, 76, 60]);
            
            doc.setTextColor(statusColor[0], statusColor[1], statusColor[2]);
            doc.text(`Question ${i+1}: ${status}`, 20, yPos);
            
            doc.setTextColor(80, 80, 80);
            doc.setFontSize(10);
            doc.text(`${questions[i].q}`, 20, yPos + 7, { maxWidth: 170 });
            
            if (userAnswers[i] !== null) {
                const userAnswerText = questions[i].options[userAnswers[i]];
                const correctAnswerText = questions[i].options[questions[i].answer];
                doc.text(`Your Answer: ${userAnswerText}`, 20, yPos + 14);
                doc.text(`Correct Answer: ${correctAnswerText}`, 20, yPos + 21);
            }
            
            yPos += 30;
            doc.setFontSize(12);
        }
        
        // Tips Page
        doc.addPage();
        doc.setFontSize(18);
        doc.setTextColor(30, 30, 30);
        doc.text('Improvement Tips', 20, 20);
        
        doc.setFontSize(12);
        doc.setTextColor(80, 80, 80);
        
        let tips = [];
        if (score.percentage >= 90) {
            tips = [
                'Excellent work! You have mastered comparative and superlative adjectives.',
                'Challenge yourself with irregular forms: good/better/best, bad/worse/worst, far/farther/farthest.',
                'Try creating your own sentences using both comparative and superlative forms.',
                'Help classmates who are struggling with these concepts.'
            ];
        } else if (score.percentage >= 70) {
            tips = [
                'Good performance! Focus on the rules you missed.',
                'Remember: 1-syllable adjectives: -er/-est, 2+ syllable adjectives: more/most.',
                'Practice with real-life examples: "My phone is newer than yours."',
                'Review irregular adjectives: good → better → best, bad → worse → worst.'
            ];
        } else {
            tips = [
                'Review basic grammar rules for comparatives and superlatives.',
                'Focus on: When to add -er/-est vs when to use more/most.',
                'Practice regularly with simple sentences first.',
                'Watch English videos or read articles to see these forms in context.'
            ];
        }
        
        yPos = 35;
        tips.forEach(tip => {
            doc.text(`• ${tip}`, 20, yPos, { maxWidth: 170 });
            yPos += 20;
        });
        
        // Footer
        doc.setFontSize(10);
        doc.setTextColor(150, 150, 150);
        doc.text('Generated by Interactive English Grammar Test System', 105, 290, null, null, 'center');
        
        // Save PDF
        const fileName = `English-Grammar-Test-${studentName.replace(/\s+/g, '-')}-${new Date().toISOString().slice(0,10)}.pdf`;
        doc.save(fileName);
        
        // Restore buttons
        shareButtons.innerHTML = originalHTML;
        
        alert(`PDF report "${fileName}" has been downloaded successfully!`);
    }, 1000);
}

// Share to WhatsApp with PDF
function shareToWhatsApp() {
    playSound('click');
    
    // First generate the PDF
    generatePDF();
    
    // Then prepare WhatsApp message
    setTimeout(() => {
        const score = calculateScore();
        const timeSpent = 15 - (timeLeft / 60);
        
        const message = `*English Grammar Test Results*
        
*Student Information:*
👤 Name: ${studentName}
🏫 Class: ${studentClass}
👨‍🏫 Teacher: Fahad Al-Khalidi

*Test Results:*
📊 Score: ${score.correct}/${score.total}
📈 Percentage: ${score.percentage}%
⭐ Evaluation: ${score.evaluation}
⏱️ Time Spent: ${timeSpent.toFixed(2)} minutes
📅 Date: ${new Date().toLocaleDateString('en-US')}

*Topic:* Comparative & Superlative Adjectives

A detailed PDF report has been generated and downloaded. Please check your downloads folder for the complete report with all questions and answers.

*Study Tips:*
${score.percentage >= 70 ? 'Great job! Keep practicing advanced grammar topics.' : 'Review basic grammar rules and practice regularly.'}`;
        
        const encodedMessage = encodeURIComponent(message);
        const whatsappURL = `https://wa.me/?text=${encodedMessage}`;
        
        // Open WhatsApp in a new window
        window.open(whatsappURL, '_blank', 'width=600,height=700');
    }, 2000);
}

// Restart Quiz
function restartQuiz() {
    playSound('click');
    
    if (!confirm("Are you sure you want to restart the test? Your current progress will be lost.")) {
        return;
    }
    
    currentQuestionIndex = 0;
    userAnswers = Array(questions.length).fill(null);
    timeLeft = 15 * 60;
    markedQuestions = [];
    answerLocked = Array(questions.length).fill(false);
    shuffledQuestions = [];
    testStarted = false;

    document.getElementById("quiz").innerHTML = '';
    document.querySelector(".controls").style.display = "flex";
    document.getElementById("result-box").style.display = "none";
    document.getElementById("advanced-results").style.display = "none";

    clearInterval(timerInterval);
    
    // Show student info form
    document.getElementById('studentInfoForm').style.display = 'block';
    document.getElementById('studentInfoDisplay').style.display = 'none';
    
    updateTimerDisplay();
    
    // Scroll to top
    window.scrollTo({ top: 0, behavior: 'smooth' });
}

// Finish Quiz
function finishQuiz() {
    if (!testStarted) {
        alert("Please start the test first by entering your information.");
        return;
    }
    
    clearInterval(timerInterval);

    const score = calculateScore();

    savePerformanceRecord();

    playSound('correct');

    document.getElementById("result-box").style.display = "block";
    document.getElementById("result").innerHTML = `${score.evaluationIcon} Score: ${score.correct} out of ${score.total}`;
    document.getElementById("percentage").innerHTML = `Percentage: ${score.percentage}%`;
    document.getElementById("evaluation").innerHTML = `Evaluation: ${score.evaluation}`;

    document.getElementById("quiz").style.display = "none";
    document.querySelector(".controls").style.display = "none";

    document.getElementById('advanced-results').style.display = 'block';

    setTimeout(() => {
        createPerformanceChart();
        createCustomTips();
    }, 100);
}

// Add Sound Effects to Buttons
document.addEventListener('DOMContentLoaded', function() {
    document.querySelectorAll('.btn').forEach(button => {
        button.addEventListener('click', () => {
            playSound('click');
        });
        
        button.addEventListener('mouseenter', () => {
            if (!button.disabled) {
                playSound('hover');
            }
        });
    });
});

// Initialize Application
window.onload = function() {
    checkDarkModePreference();
    loadPerformanceHistory();
    
    // Load student info if exists
    if (loadStudentInfo()) {
        // Auto-start if info exists
        testStarted = true;
        loadQuiz();
        startTimer();
    }
    
    const savedSoundSetting = localStorage.getItem('soundEnabled');
    if (savedSoundSetting !== null) {
        soundEnabled = savedSoundSetting === 'true';
    }
    
    const soundBtn = document.getElementById('soundToggleBtn');
    const soundIcon = soundBtn.querySelector('i');
    const soundStatus = soundBtn.nextElementSibling;
    
    if (soundEnabled) {
        soundIcon.classList.remove('fa-volume-mute');
        soundIcon.classList.add('fa-volume-up');
        soundBtn.classList.remove('muted');
        soundStatus.textContent = 'Sounds On';
    } else {
        soundIcon.classList.remove('fa-volume-up');
        soundIcon.classList.add('fa-volume-mute');
        soundBtn.classList.add('muted');
        soundStatus.textContent = 'Sounds Off';
    }
    
    initSounds();
    
    if (testStarted) {
        loadQuiz();
        startTimer();
    }

    document.querySelector('.hero-section').classList.add('bounce-in');
    setTimeout(() => {
        if (document.querySelector('.card')) {
            document.querySelector('.card').classList.add('fade-in');
        }
    }, 300);
    
    window.onclick = function(event) {
        const currentScoreModal = document.getElementById('currentScoreModal');
        const questionsModal = document.getElementById('questionsModal');
        
        if (event.target == currentScoreModal) {
            currentScoreModal.style.display = 'none';
        }
        
        if (event.target == questionsModal) {
            questionsModal.style.display = 'none';
        }
    }
}
</script>
</body>
</html>

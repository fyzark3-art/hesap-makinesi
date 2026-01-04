# hesap-makinesi* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
}

.calculator-container {
    perspective: 1000px;
}

.calculator {
    background: rgba(20, 20, 30, 0.95);
    backdrop-filter: blur(10px);
    border-radius: 25px;
    padding: 30px;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5),
                0 0 50px rgba(102, 126, 234, 0.3);
    border: 2px solid rgba(255, 255, 255, 0.1);
    width: 380px;
    max-width: 100%;
    transition: transform 0.3s ease;
}

.calculator:hover {
    transform: translateY(-5px);
}

.display {
    background: rgba(0, 0, 0, 0.5);
    border-radius: 15px;
    padding: 25px 20px;
    margin-bottom: 25px;
    border: 2px solid rgba(255, 255, 255, 0.1);
    box-shadow: inset 0 2px 10px rgba(0, 0, 0, 0.5);
    min-height: 100px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
}

.display-text {
    color: #00ff88;
    font-size: 42px;
    font-weight: 300;
    text-align: right;
    word-wrap: break-word;
    word-break: break-all;
    text-shadow: 0 0 20px rgba(0, 255, 136, 0.5);
    font-family: 'Courier New', monospace;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 15px;
}

.btn {
    background: linear-gradient(145deg, #2a2a3a, #1a1a2a);
    border: 2px solid rgba(255, 255, 255, 0.1);
    border-radius: 15px;
    color: #ffffff;
    font-size: 24px;
    font-weight: 600;
    padding: 25px;
    cursor: pointer;
    transition: all 0.2s ease;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3),
                inset 0 1px 0 rgba(255, 255, 255, 0.1);
    position: relative;
    overflow: hidden;
    text-transform: none;
    font-family: 'Segoe UI', sans-serif;
}

.btn::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    width: 0;
    height: 0;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.2);
    transform: translate(-50%, -50%);
    transition: width 0.6s, height 0.6s;
}

.btn:active::before {
    width: 300px;
    height: 300px;
}

.btn.number {
    background: linear-gradient(145deg, #2a2a3a, #1a1a2a);
    color: #ffffff;
}

.btn.number:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4),
                0 0 30px rgba(102, 126, 234, 0.3);
}

.btn.operator {
    background: linear-gradient(145deg, #3a3a4a, #2a2a3a);
    color: #ff6b9d;
}

.btn.operator:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(255, 107, 157, 0.4),
                0 0 30px rgba(255, 107, 157, 0.3);
}

.btn.equals {
    background: linear-gradient(145deg, #667eea, #764ba2);
    color: #ffffff;
    grid-column: span 1;
}

.btn.equals:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(102, 126, 234, 0.6),
                0 0 40px rgba(102, 126, 234, 0.5);
}

.btn.zero {
    grid-column: span 1;
}

.btn:active {
    transform: scale(0.95) translateY(0);
}

/* RGB Animation Classes */
.btn.rgb-animate {
    animation: rgbPulse 0.6s ease;
}

@keyframes rgbPulse {
    0% {
        box-shadow: 0 0 0 0 rgba(255, 0, 0, 0.7);
    }
    33% {
        box-shadow: 0 0 0 10px rgba(0, 255, 0, 0.4),
                    0 0 0 20px rgba(0, 255, 0, 0.2);
    }
    66% {
        box-shadow: 0 0 0 10px rgba(0, 0, 255, 0.4),
                    0 0 0 20px rgba(0, 0, 255, 0.2);
    }
    100% {
        box-shadow: 0 0 0 0 rgba(255, 0, 0, 0);
    }
}

/* Background RGB Animation */
body.rgb-mode {
    animation: rgbBackground 10s ease infinite;
}

@keyframes rgbBackground {
    0% {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    }
    33% {
        background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
    }
    66% {
        background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
    }
    100% {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    }
}

/* Responsive Design */
@media (max-width: 480px) {
    .calculator {
        padding: 20px;
        width: 100%;
    }
    
    .btn {
        padding: 20px;
        font-size: 20px;
    }
    
    .display-text {
        font-size: 36px;
    }
}



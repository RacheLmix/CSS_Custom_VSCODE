/* Hiệu ứng hover cho thanh sidebar */
.sidebar {
    transition: transform 0.5s ease-in-out;
}

.sidebar:hover {
    transform: scale(1.01);
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

/* Hiệu ứng cho tab đang hoạt động */
.tab.active {
    animation: pulse 1.5s infinite;
}

@keyframes pulse {
    0% {
        box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
    }
    50% {
        box-shadow: 0 0 15px rgba(0, 123, 255, 0.8);
    }
    100% {
        box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
    }
}

/* Hiệu ứng cho dòng code khi được highlight */
.monaco-editor .focused .selected-text {
    background-color: rgba(255, 230, 0, 0.5);
    animation: glow 1s infinite alternate;
}

@keyframes glow {
    from {
        background-color: rgba(95, 51, 255, 0.5);
    }
    to {
        background-color: rgba(221, 0, 255, 0.8);
    }
}

/* Hiệu ứng khi mở terminal */
.terminal {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.5s ease, transform 0.5s ease;
}

.terminal.visible {
    opacity: 1;
    transform: translateY(0);
}

/* Hiệu ứng loading cho status bar */
.statusbar {
    position: relative;
}

.statusbar::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, transparent, #007acc, transparent);
    animation: loading 2s infinite;
}

@keyframes loading {
    0% {
        transform: translateX(-100%);
    }
    100% {
        transform: translateX(100%);
    }
}
/* Hiệu ứng hai vòng glow chạy quanh khung tab */
.tab {
    position: relative;
    overflow: hidden;
}

.tab::before,
.tab::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 200%;
    height: 200%;
    background: linear-gradient(
        45deg,
        rgba(0, 123, 255, 0.5),
        rgba(255, 255, 255, 0),
        rgba(0, 123, 255, 0.5)
    );
    transform-origin: center;
    animation: rotateGlow 4s infinite linear;
    z-index: -1;
    border-radius: 50%;
}

.tab::after {
    animation: rotateGlowReverse 6s infinite linear;
}

@keyframes rotateGlow {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}

@keyframes rotateGlowReverse {
    from {
        transform: rotate(360deg);
    }
    to {
        transform: rotate(0deg);
    }
}

/* Hiệu ứng phát sáng cho dấu ngoặc */
.monaco-editor .bracket-match {
    background-color: rgba(0, 255, 128, 0.3); /* Màu xanh lá nhạt */
    border-radius: 2px;
    animation: glow-brackets 1s infinite alternate;
}

@keyframes glow-brackets {
    from {
        background-color: rgba(0, 255, 128, 0.3);
    }
    to {
        background-color: rgba(0, 255, 128, 0.6);
    }
}
/* Hiệu ứng cho dòng code hiện tại */
.monaco-editor .view-overlays .current-line {
    background-color: rgba(0, 123, 255, 0.1); /* Màu xanh nhạt */
    animation: pulse-line 1.5s infinite;
}

@keyframes pulse-line {
    0% {
        background-color: rgba(0, 123, 255, 0.1);
    }
    50% {
        background-color: rgba(0, 123, 255, 0.3);
    }
    100% {
        background-color: rgba(0, 123, 255, 0.1);
    }
}

/* Hiệu ứng nhấp nháy cho con trỏ */
.monaco-editor .cursor {
    animation: blink 1s infinite;
}

@keyframes blink {
    0%, 100% {
        opacity: 1;
    }
    50% {
        opacity: 0;
    }
}

/* Hiệu ứng phát sáng cho con trỏ */
.monaco-editor .cursor {
    background-color: #ff4d4d; /* Màu đỏ */
    box-shadow: 0 0 8px rgba(255, 77, 77, 0.8);
    animation: glow-cursor 1.5s infinite alternate;
}

@keyframes glow-cursor {
    from {
        box-shadow: 0 0 8px rgba(255, 77, 77, 0.8);
    }
    to {
        box-shadow: 0 0 16px rgba(255, 77, 77, 1);
    }
}

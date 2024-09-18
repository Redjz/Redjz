const scenes = [
    "A young boy finds himself lost in the heart of a dense jungle. The towering trees and distant animal sounds surround him.",
    "He remembers his survival lessons and begins to search for food and water. The jungle is both beautiful and dangerous.",
    "As night falls, he builds a small shelter using branches and leaves. Strange glowing eyes peer at him from the darkness.",
    "The boy befriends a curious monkey, which shows him hidden paths through the jungle.",
    "Together, they discover an ancient ruin deep within the jungle. What secrets does it hold?",
    "As a storm brews overhead, the boy must find shelter quickly or face the fury of the jungle."
];

let currentScene = 0;
const sceneText = document.getElementById('scene-text');
const nextButton = document.getElementById('next-btn');

nextButton.addEventListener('click', () => {
    if (currentScene < scenes.length - 1) {
        currentScene++;
        sceneText.innerText = scenes[currentScene];
        fadeInEffect();
    } else {
        sceneText.innerText = "The End. The boy has learned the ways of the jungle.";
        nextButton.disabled = true;
        nextButton.innerText = "Finished";
    }
});

function fadeInEffect() {
    const storyElement = document.getElementById('story');
    storyElement.classList.remove('visible');
    setTimeout(() => {
        storyElement.classList.add('visible');
    }, 50);
}

window.onload = () => {
    fadeInEffect();
};

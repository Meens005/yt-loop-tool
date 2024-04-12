// Function to generate a timestamped URL for a YouTube video
function generateYoutubeTimestampUrl(videoId, startMin, startSec, endMin, endSec) {
    const startTime = startMin * 60 + startSec;
    const endTime = endMin * 60 + endSec;
    return `https://www.youtube.com/watch?v=${videoId}&start=${startTime}&end=${endTime}`;
}

// Read the YouTube video URL from the user
const videoUrl = prompt("Enter the YouTube video URL:");

// Extract the video ID from the URL using a regular expression
const match = videoUrl.match(/(?<=v=)[\w-]+/);
let videoId;
if (match) {
    videoId = match[0];
} else {
    alert("Invalid YouTube video URL.");
    throw new Error("Invalid YouTube video URL.");
}

// Read start and end times from the user
const startMin = parseInt(prompt("Enter the start minute:"));
const startSec = parseInt(prompt("Enter the start second:"));
const endMin = parseInt(prompt("Enter the end minute:"));
const endSec = parseInt(prompt("Enter the end second:"));

// Generate the timestamp URL
const timestampUrl = generateYoutubeTimestampUrl(videoId, startMin, startSec, endMin, endSec);
alert("Timestamp URL: " + timestampUrl);
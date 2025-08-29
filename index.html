<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz Master</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.9.0/dist/confetti.browser.min.js"></script>
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, doc, getDoc, setDoc, addDoc, onSnapshot, collection, query, orderBy, limit, deleteDoc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";
        import { setLogLevel } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // Firebase setup and global variables
        setLogLevel('Debug');
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';
        const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : {};
        const initialAuthToken = typeof __initial_auth_token !== 'undefined' ? __initial_auth_token : null;

        let app, db, auth, userId;
        let isAuthReady = false;

        const quizData = {
    'পদার্থবিজ্ঞান প্রথম পত্র': {
        name: 'পদার্থবিজ্ঞান প্রথম পত্র',
        type: 'academic',
        chapters: {
            'ভৌতজগত ও পরিমাপ': [
                { question: "ভৌতজগতের সংজ্ঞা কী?", answers: ["পদার্থ এবং শক্তি", "জীবন এবং শক্তি", "স্থান এবং সময়", "নিয়ম এবং নীতি"], correct: "পদার্থ এবং শক্তি" }
            ],
            'ভেক্টর': [
                { question: "কোন রাশিটি ভেক্টর?", answers: ["সময়", "ভর", "সরণ", "তাপমাত্রা"], correct: "সরণ" }
            ],
            'গতিবিদ্যা': [
                { question: "গতির সমীকরণগুলো কীসের উপর নির্ভরশীল?", answers: ["ভর", "সময়", "বল", "কাজ"], correct: "সময়" }
            ],
            'নিউটোনীয়ান বলবিদ্যা': [
                { question: "নিউটনের প্রথম সূত্র কীসের সাথে সম্পর্কিত?", answers: ["বল", "ভর", "নিষ্ক্রিয়তা", "বেগ"], correct: "নিষ্ক্রিয়তা" }
            ],
            'কাজ, শক্তি ও ক্ষমতা': [
                { question: "শক্তির একক কী?", answers: ["ওয়াট", "জুল", "নিউটন", "ভোল্ট"], correct: "জুল" }
            ],
            'মহাকর্ষ ও অভিকর্ষ': [
                { question: "মহাকর্ষের সূত্র কে আবিষ্কার করেন?", answers: ["আইনস্টাইন", "গ্যালিলিও", "নিউটন", "আর্কিমিডিস"], correct: "নিউটন" }
            ],
            'পদার্থের গাঠনিক ধর্ম': [
                { question: "স্থিতিস্থাপকতার সংজ্ঞা কী?", answers: ["বিকৃতি", "বল", "আয়তন", "প্রান্তিক চাপ"], correct: "আয়তন" }
            ],
            'পর্যাবৃত্ত গতি': [
                { question: "দোলকের গতি কীসের উদাহরণ?", answers: ["রৈখিক গতি", "ঘূর্ণন গতি", "পর্যাবৃত্ত গতি", "প্রক্ষেপন গতি"], correct: "পর্যাবৃত্ত গতি" }
            ],
            'তরঙ্গ': [
                { question: "আলো কী ধরনের তরঙ্গ?", answers: ["অনুপ্রস্থ", "অনু-দৈর্ঘ্য", "উভয়ই", "কোনটিই নয়"], correct: "অনুপ্রস্থ" }
            ],
            'আদর্শ গ্যাস ও গ্যাসের গতিতত্ত্ব': [
                { question: "আদর্শ গ্যাসের গতিতত্ত্বের মূলনীতি কোনটি?", answers: ["চাপ এবং তাপমাত্রা", "গ্যাসের ঘনত্ব", "তাপমাত্রা এবং আয়তন", "তাপমাত্রা"], correct: "চাপ এবং তাপমাত্রা" }
            ],
        }
    },
    'পদার্থবিজ্ঞান দ্বিতীয় পত্র': {
        name: 'পদার্থবিজ্ঞান দ্বিতীয় পত্র',
        type: 'academic',
        chapters: {
            'তাপগতিবিদ্যা': [
                { question: "তাপগতিবিদ্যার প্রথম সূত্র কী?", answers: ["শক্তির সংরক্ষণ", "চার্জের সংরক্ষণ", "বলের সংরক্ষণ", "চাপের সংরক্ষণ"], correct: "শক্তির সংরক্ষণ" }
            ],
            'স্থিরতড়িৎ': [
                { question: "স্থিরতড়িতের মূলনীতি কী?", answers: ["ফোর্স", "ভোল্টেজ", "চার্জ", "ক্ষমতা"], correct: "চার্জ" }
            ],
            'চলতড়িৎ': [
                { question: "ওহমের সূত্র কীসের সম্পর্ক স্থাপন করে?", answers: ["ভোল্টেজ ও কারেন্ট", "ভোল্টেজ ও প্রতিরোধ", "কারেন্ট ও তাপমাত্রা", "কারেন্ট ও ক্ষমতা"], correct: "ভোল্টেজ ও কারেন্ট" }
            ],
            'তড়িৎ প্রবাহের চৌম্বক ক্রিয়া ও চুম্বকত্ব': [
                { question: "একটি চলন্ত চার্জ কী তৈরি করে?", answers: ["স্থিরতড়িৎ", "চলতড়িৎ", "চৌম্বক ক্ষেত্র", "তাপ"], correct: "চৌম্বক ক্ষেত্র" }
            ],
            'তাড়িতচৌম্বক আবেশ ও পরিবর্তী প্রবাহ': [
                { question: "তাড়িতচৌম্বক আবেশের মূলনীতি কে আবিষ্কার করেন?", answers: ["ওহম", "ফ্যারাডে", "আর্কিমিডিস", "নিউটন"], correct: "ফ্যারাডে" }
            ],
            'জ্যামিতিক আলোকবিজ্ঞান': [
                { question: "একটি লেন্সের ফোকাস দূরত্ব কীসের উপর নির্ভর করে?", answers: ["আকার", "উপাদান", "আকার ও উপাদান", "আলোর গতি"], correct: "আকার ও উপাদান" }
            ],
            'ভৌত আলোকবিজ্ঞান': [
                { question: "আলোর তরঙ্গদৈর্ঘ্য পরিমাপ করতে কী ব্যবহার করা হয়?", answers: ["আয়তন", "তরঙ্গমাপক", "অপবর্তন গ্রেটিং", "ফোকাস দূরত্ব"], correct: "অপবর্তন গ্রেটিং" }
            ],
            'আধুনিক পদার্থবিজ্ঞানের সূচনা': [
                { question: "ফোটন কী?", answers: ["কণা", "তরঙ্গ", "শক্তি", "কণা এবং তরঙ্গ উভয়ই"], correct: "কণা" }
            ],
            'পরমাণু মডেল এবং নিউক্লিয়ার পদার্থবিজ্ঞান': [
                { question: "নিউক্লিয়াসে কোন কণাগুলো থাকে?", answers: ["ইলেকট্রন ও প্রোটন", "ইলেকট্রন ও নিউট্রন", "প্রোটন ও নিউট্রন", "শুধুমাত্র প্রোটন"], correct: "প্রোটন ও নিউট্রন" }
            ],
            'সেমিকন্ডাক্টর ও ইলেকট্রনিক্স': [
                { question: "ট্রানজিস্টরের প্রধান কাজ কী?", answers: ["পরিবাহিতা", "রোধ", "অর্ধপরিবাহিতা", "প্রবর্ধন"], correct: "প্রবর্ধন" }
            ],
            'জ্যোতির্বিজ্ঞান': [
                { question: "সূর্য কী দিয়ে গঠিত?", answers: ["গ্যাস", "ধুলিকণা", "হিম", "গ্যাস এবং ধুলিকণা"], correct: "গ্যাস" }
            ],
        }
    },
    'রসায়ন প্রথম পত্র': {
        name: 'রসায়ন প্রথম পত্র',
        type: 'academic',
        chapters: {
            'ল্যাবরেটরির নিরাপদ ব্যবহার': [
                { question: "কোন ধরনের গ্লাসওয়্যার উত্তপ্ত করার জন্য সবচেয়ে নিরাপদ?", answers: ["বিকার", "ফ্লাস্ক", "বুরেট", "পিপ্রেট"], correct: "ফ্লাস্ক" }
            ],
            'গুণগত রসায়ন': [
                { question: "পারমাণবিক মডেলের আবিষ্কারক কে?", answers: ["রাদারফোর্ড", "বোর", "ডাল্টন", "থমসন"], correct: "রাদারফোর্ড" }
            ],
            'মৌলের পর্যায়বৃত্ত ধর্ম ও রাসায়নিক বন্ধন': [
                { question: "কোন ধরনের বন্ধন দুটি অধাতুর মধ্যে গঠিত হয়?", answers: ["আয়নিক", "সমযোজী", "ধাতব", "হাইড্রোজেন"], correct: "সমযোজী" }
            ],
            'রাসায়নিক পরিবর্তন': [
                { question: "একটি রাসায়নিক বিক্রিয়ায় কোনটির পরিমাণ অপরিবর্তিত থাকে?", answers: ["ভর", "আয়তন", "তাপমাত্রা", "চাপ"], correct: "ভর" }
            ],
            'কর্মমুখী রসায়ন': [
                { question: "ব্লিচিং পাউডারের রাসায়নিক নাম কী?", answers: ["ক্যালসিয়াম ক্লোরাইড", "ক্যালসিয়াম হাইপোক্লোরাইট", "সোডিয়াম ক্লোরাইড", "সোডিয়াম হাইপোক্লোরাইট"], correct: "ক্যালসিয়াম হাইপোক্লোরাইট" }
            ]
        }
    },
    'রসায়ন দ্বিতীয় পত্র': {
        name: 'রসায়ন দ্বিতীয় পত্র',
        type: 'academic',
        chapters: {
            'পরিবেশ রসায়ন': [
                { question: "গ্রিনহাউস গ্যাস কোনটি?", answers: ["অক্সিজেন", "নাইট্রোজেন", "কার্বন ডাই অক্সাইড", "হাইড্রোজেন"], correct: "কার্বন ডাই অক্সাইড" }
            ],
            'জৈব রসায়ন': [
                { question: "মিথেনের রাসায়নিক সংকেত কী?", answers: ["$C_2H_6$", "$CH_4$", "$C_3H_8$", "$C_4H_{10}$"], correct: "$CH_4$" }
            ],
            'পরিমাণগত রসায়ন': [
                { question: "মোলারিটির একক কী?", answers: ["গ্রাম/লিটার", "মোল/লিটার", "মোল", "লিটার"], correct: "মোল/লিটার" }
            ],
            'তড়িৎ রসায়ন': [
                { question: "কোন প্রক্রিয়ায় রাসায়নিক শক্তি তড়িৎ শক্তিতে রূপান্তরিত হয়?", answers: ["তড়িৎ বিশ্লেষণ", "তড়িৎ রাসায়নিক কোষ", "জারণ", "বিজারণ"], correct: "তড়িৎ রাসায়নিক কোষ" }
            ],
            'অর্থনৈতিক রসায়ন': [
                { question: "সিমেন্ট উৎপাদনে কোন দুটি প্রধান উপাদান ব্যবহৃত হয়?", answers: ["চুনাপাথর ও কাদা", "বালি ও চুনাপাথর", "কাদা ও বালি", "চুনাপাথর ও আয়রন"], correct: "চুনাপাথর ও কাদা" }
            ]
        }
    },
    'জীববিজ্ঞান প্রথম পত্র': {
        name: 'জীববিজ্ঞান প্রথম পত্র',
        type: 'academic',
        chapters: {
            'কোষ ও এর গঠন': [
                { question: "কোষের শক্তিঘর কোনটি?", answers: ["নিউক্লিয়াস", "মাইটোকন্ড্রিয়া", "রাইবোসোম", "গলজি বস্তু"], correct: "মাইটোকন্ড্রিয়া" }
            ],
            'কোষ বিভাজন': [
                { question: "কোন ধরনের কোষ বিভাজনে একটি কোষ থেকে দুটি হুবহু একই রকম অপত্য কোষ সৃষ্টি হয়?", answers: ["মিয়োসিস", "মাইটোসিস", "এমাইটোসিস", "সাইটোসিস"], correct: "মাইটোসিস" }
            ],
            'কোষ রসায়ন': [
                { question: "কোন জৈব অণু জেনেটিক তথ্য ধারণ করে?", answers: ["প্রোটিন", "ডিএনএ", "কার্বোহাইড্রেট", "লিপিড"], correct: "ডিএনএ" }
            ],
            'অণুজীব': [
                { question: "ব্যাকটেরিয়া কী?", answers: ["বহুকোষী জীব", "এককোষী জীব", "ভাইরাস", "ছত্রাক"], correct: "এককোষী জীব" }
            ],
            'শৈবাল ও ছত্রাক': [
                { question: "কোনটি উদ্ভিদ-সদৃশ প্রোটিস্ট?", answers: ["শৈবাল", "ছত্রাক", "ব্যাকটেরিয়া", "ভাইরাস"], correct: "শৈবাল" }
            ],
            'ব্রায়োফাইটা ও টেরিডোফাইটা': [
                { question: "মস হলো কোন ধরনের উদ্ভিদ?", answers: ["শৈবাল", "ব্রায়োফাইটা", "টেরিডোফাইটা", "নগ্নবীজী"], correct: "ব্রায়োফাইটা" }
            ],
            'নগ্নবীজী ও আবৃতবীজী উদ্ভিদ': [
                { question: "আবৃতবীজী উদ্ভিদের একটি প্রধান বৈশিষ্ট্য কী?", answers: ["নগ্ন বীজ", "আচ্ছাদিত বীজ", "স্পোর", "ফল"], correct: "আচ্ছাদিত বীজ" }
            ],
            'টিস্যু ও টিস্যুতন্ত্র': [
                { question: "জাইলেম টিস্যুর প্রধান কাজ কী?", answers: ["খাদ্য পরিবহন", "পানি পরিবহন", "খাদ্য সঞ্চয়", "টিস্যু রক্ষা"], correct: "পানি পরিবহন" }
            ],
            'উদ্ভিদ শারীরতত্ত্ব': [
                { question: "সালোকসংশ্লেষণ কী?", answers: ["খাদ্য তৈরি প্রক্রিয়া", "শ্বাস-প্রশ্বাস প্রক্রিয়া", "পানি শোষণ প্রক্রিয়া", "বংশবৃদ্ধি প্রক্রিয়া"], correct: "খাদ্য তৈরি প্রক্রিয়া" }
            ],
            'উদ্ভিদ প্রজনন': [
                { question: "ফুলের পুংজনন অঙ্গ কোনটি?", answers: ["পাপড়ি", "গর্ভাশয়", "পুংকেশর", "বৃতি"], correct: "পুংকেশর" }
            ],
            'জীবপ্রযুক্তি': [
                { question: "জেনেটিক ইঞ্জিনিয়ারিং কী?", answers: ["জিন পরিবর্তন", "জিনের নাম", "জিনের গঠন", "জিনের ব্যবহার"], correct: "জিন পরিবর্তন" }
            ]
        }
    },
    'জীববিজ্ঞান দ্বিতীয় পত্র': {
        name: 'জীববিজ্ঞান দ্বিতীয় পত্র',
        type: 'academic',
        chapters: {
            'প্রাণীর বিভিন্নতা ও শ্রেণিবিন্যাস': [
                { question: "শ্রেণিবিন্যাস পদ্ধতির সর্বোচ্চ ধাপ কোনটি?", answers: ["পরিবার", "গোত্র", "রাজ্য", "বর্গ"], correct: "রাজ্য" }
            ],
            'প্রাণীর পরিচিতি': [
                { question: "কোন পর্বের প্রাণীর দেহে সংযুক্ত পা থাকে?", answers: ["আর্থ্রোপোডা", "অ্যানিলিডা", "মলাস্কা", "প্ল্যাটিহেলমিন্থেস"], correct: "আর্থ্রোপোডা" }
            ],
            'মানব শারীরতত্ত্ব: পরিপাক ও শোষণ': [
                { question: "ক্ষুদ্রান্ত্রের প্রধান কাজ কী?", answers: ["খাদ্য চর্বন", "খাদ্য পরিপাক", "খাদ্য শোষণ", "খাদ্য সংরক্ষণ"], correct: "খাদ্য শোষণ" }
            ],
            'মানব শারীরতত্ত্ব: রক্ত ও সংবহন': [
                { question: "কোন রক্তকোষ অক্সিজেন পরিবহন করে?", answers: ["লোহিত রক্তকণিকা", "শ্বেত রক্তকণিকা", "অনুচক্রিকা", "প্লাজমা"], correct: "লোহিত রক্তকণিকা" }
            ],
            'মানব শারীরতত্ত্ব: শ্বাসক্রিয়া ও শ্বসন': [
                { question: "ফুসফুসের প্রধান কাজ কী?", answers: ["রক্ত পরিশোধন", "কার্বন ডাই অক্সাইড গ্রহণ", "গ্যাস বিনিময়", "অক্সিজেন পরিবহন"], correct: "গ্যাস বিনিময়" }
            ],
            'মানব শারীরতত্ত্ব: বর্জ্য ও নিষ্কাশন': [
                { question: "কোন অঙ্গ রক্ত থেকে বর্জ্য অপসারণ করে মূত্র তৈরি করে?", answers: ["যকৃত", "ফুসফুস", "কিডনি", "হৃদপিণ্ড"], correct: "কিডনি" }
            ],
            'মানব শারীরতত্ত্ব: চলন ও অঙ্গচালনা': [
                { question: "একটি কঙ্কালের প্রধান কাজ কী?", answers: ["রক্ত উৎপাদন", "খাদ্য হজম", "দেহকে সমর্থন", "চাপ নিয়ন্ত্রণ"], correct: "দেহকে সমর্থন" }
            ],
            'মানব শারীরতত্ত্ব: সমন্বয় ও নিয়ন্ত্রণ': [
                { question: "স্নায়ুতন্ত্রের প্রধান অঙ্গ কোনটি?", answers: ["হৃদপিণ্ড", "মস্তিষ্ক", "ফুসফুস", "কিডনি"], correct: "মস্তিষ্ক" }
            ],
            'মানব জীবনের ধারাবাহিকতা': [
                { question: "জেনেটিক তথ্য ধারণ করে কোন অঙ্গাণু?", answers: ["মাইটোকন্ড্রিয়া", "রাইবোসোম", "ক্রোমোসোম", "গলজি বডি"], correct: "ক্রোমোসোম" }
            ],
            'প্রতিরক্ষা': [
                { question: "শরীরের প্রথম প্রতিরক্ষা ব্যবস্থা কোনটি?", answers: ["চামড়া", "লোহিত রক্তকণিকা", "মস্তিষ্ক", "ফুসফুস"], correct: "চামড়া" }
            ],
            'জিনতত্ত্ব ও বিবর্তন': [
                { question: "জিনতত্ত্বের জনক কে?", answers: ["চার্লস ডারউইন", "গ্রেগর মেন্ডেল", "আর্নেস্ট হেকেল", "লুই পাস্তুর"], correct: "গ্রেগর মেন্ডেল" }
            ],
            'প্রাণীর আচরণ': [
                { question: "কোনটি একটি অর্জিত আচরণ?", answers: ["প্রতিফলিত ক্রিয়া", "আচরণ", "শিখন", "অভ্যাস"], correct: "শিখন" }
            ]
        }
    },
    'উচ্চতর গণিত প্রথম পত্র': {
        name: 'উচ্চতর গণিত প্রথম পত্র',
        type: 'academic',
        chapters: {
            'ম্যাট্রিক্স ও নির্ণায়ক': [
                { question: "একটি ম্যাট্রিক্সের নির্ণায়ক কী?", answers: ["একটি ম্যাট্রিক্স", "একটি ভেক্টর", "একটি স্কেলার মান", "একটি সেট"], correct: "একটি স্কেলার মান" }
            ],
            'ভেক্টর': [
                { question: "একটি ভেক্টরের বৈশিষ্ট্য কী?", answers: ["শুধুমাত্র দিক", "শুধুমাত্র মান", "মান এবং দিক উভয়ই", "কোনটিই নয়"], correct: "মান এবং দিক উভয়ই" }
            ],
            'সরলরেখা': [
                { question: "একটি সরলরেখার ঢাল কী?", answers: ["y এর পরিবর্তন / x এর পরিবর্তন", "y এর পরিবর্তন", "x এর পরিবর্তন", "স্থানাঙ্ক"], correct: "y এর পরিবর্তন / x এর পরিবর্তন" }
            ],
            'বৃত্ত': [
                { question: "$(h,k)$ কেন্দ্র এবং $r$ ব্যাসার্ধ বিশিষ্ট বৃত্তের সমীকরণ কী?", answers: ["$(x-h)^2 + (y-k)^2 = r^2$", "$x^2 + y^2 = r^2$", "$(x+h)^2 + (y+k)^2 = r^2$", "$x^2 - y^2 = r^2$"], correct: "$(x-h)^2 + (y-k)^2 = r^2$" }
            ],
            'সংযুক্ত কোণের ত্রিকোণমিতিক অনুপাত': [
                { question: "$\sin(A+B)$ এর সম্প্রসারণ কী?", answers: ["$\sin A \cos B + \cos A \sin B$", "$\sin A \cos B - \cos A \sin B$", "$\cos A \cos B + \sin A \sin B$", "$\cos A \cos B - \sin A \sin B$"], correct: "$\sin A \cos B + \cos A \sin B$" }
            ],
            'অন্তরীকরণ': [
                { question: "যদি $y=x^2$ হয়, তাহলে $dy/dx$ কী হবে?", answers: ["$x$", "$2x$", "$x^2$", "$1$"], correct: "$2x$" }
            ],
            'যোগজীকরণ': [
                { question: "$2x$ এর যোগজীকরণ কী?", answers: ["$x$", "$x^2+C$", "$2x^2$", "$2x+C$"], correct: "$x^2+C$" }
            ],
            'কণিক': [
                { question: "একটি বৃত্তের উৎকেন্দ্রতা কত?", answers: ["$0$", "$1$", "$-1$", "$\infty$"], correct: "$0$" }
            ],
            'ত্রিকোণমিতি': [
                { question: "$\tan(90^\circ)$ এর মান কত?", answers: ["$0$", "$1$", "$\infty$", "অসংজ্ঞায়িত"], correct: "অসংজ্ঞায়িত" }
            ]
        }
    },
    'উচ্চতর গণিত দ্বিতীয় পত্র': {
        name: 'উচ্চতর গণিত দ্বিতীয় পত্র',
        type: 'academic',
        chapters: {
            'বাস্তব সংখ্যা ও অসমতা': [
                { question: "অসমতা $x+2 > 5$ সমাধান করলে কী হবে?", answers: ["$x>3$", "$x<3$", "$x=3$", "$x>7$"], correct: "$x>3$" }
            ],
            'যোগজীকরণ': [
                { question: "$\cos(x)$ এর অনির্দিষ্ট যোগজীকরণ কী?", answers: ["$\sin(x)$", "$-\sin(x)+C$", "$\sin(x)+C$", "$-\sin(x)$"], correct: "$\sin(x)+C$" }
            ],
            'বহুপদী ও বহুপদী সমীকরণ': [
                { question: "বহুপদী $x^3+2x+1$ এর মাত্রা কত?", answers: ["$1$", "$2$", "$3$", "$4$"], correct: "$3$" }
            ],
            'সদস্য এবং লঘুকরণ': [
                { question: "দুটি সেট $A$ এবং $B$ এর সংযোগ সেট কোনটি?", answers: ["$A \cap B$", "$A \cup B$", "$A-B$", "$B-A$"], correct: "$A \cup B$" }
            ],
        }
    },
    'তথ্য ও যোগাযোগ প্রযুক্তি': {
        name: 'তথ্য ও যোগাযোগ প্রযুক্তি',
        type: 'academic',
        chapters: {
            'তথ্য ও যোগাযোগ প্রযুক্তি: বিশ্ব ও বাংলাদেশ প্রেক্ষিত': [
                { question: "ICT এর পূর্ণরূপ কী?", answers: ["Information and Communication Technology", "Indian Communication Technology", "Information and Computer Technology", "Internet Communication Tools"], correct: "Information and Communication Technology" }
            ],
            'কম্পিউটার সিস্টেম': [
                { question: "কম্পিউটারের মস্তিষ্ক কোনটি?", answers: ["মাউস", "কীবোর্ড", "সিপিইউ", "মনিটর"], correct: "সিপিইউ" }
            ],
            'ওয়েব ডিজাইন পরিচিতি এবং HTML': [
                { question: "হাইপারলিংক তৈরি করতে কোন HTML ট্যাগ ব্যবহার করা হয়?", answers: ["$<p>$", "$<h1>$", "$<a>$", "$<src>$"], correct: "$<a>$" }
            ],
            'প্রোগ্রামিং ভাষা': [
                { question: "ভেরিয়েবল কী?", answers: ["একটি প্রোগ্রাম", "একটি ডেটা সংরক্ষণের স্থান", "একটি ফাংশন", "একটি ক্লাস"], correct: "একটি ডেটা সংরক্ষণের স্থান" }
            ],
            'ডেটাবেজ ম্যানেজমেন্ট সিস্টেম': [
                { question: "একটি ডেটাবেজের প্রধান কাজ কী?", answers: ["ছবি তৈরি করা", "ডেটা সঞ্চয় ও পরিচালনা করা", "অডিও চালানো", "ভিডিও তৈরি করা"], correct: "ডেটা সঞ্চয় ও পরিচালনা করা" }
            ]
        }
    },
    'ইঞ্জিনিয়ারিং ভর্তি পরীক্ষা': {
        name: 'ইঞ্জিনিয়ারিং ভর্তি পরীক্ষা',
        type: 'admission',
        admissionType: 'Engineering',
        chapters: {
            'পদার্থবিজ্ঞান': [
                { question: "কোনো বস্তুর সরণের হার কী?", answers: ["বেগ", "ত্বরণ", "গতি", "মন্দন"], correct: "বেগ" }
            ]
        }
    },
    'মেডিকেল ভর্তি পরীক্ষা': {
        name: 'মেডিকেল ভর্তি পরীক্ষা',
        type: 'admission',
        admissionType: 'Medical',
        chapters: {
            'জীববিজ্ঞান': [
                { question: "কোনটি DNA এর উপাদান নয়?", answers: ["অ্যাডেনিন", "গুয়ানিন", "ইউরাসিল", "সাইটোসিন"], correct: "ইউরাসিল" }
            ]
        }
    },
    'ভার্সিটি ভর্তি পরীক্ষা': {
        name: 'ভার্সিটি ভর্তি পরীক্ষা',
        type: 'admission',
        admissionType: 'Varsity',
        chapters: {
            'বাংলা': [
                { question: "কোনটি রবীন্দ্রনাথ ঠাকুরের লেখা?", answers: ["সঞ্চয়িতা", "সঞ্চয়িতা (সম্পাদিত)", "সোনার তরী", "সঞ্চয়িতা (রবীন্দ্র কাব্য)"], correct: "সোনার তরী" }
            ]
        }
    }
};


        // App state
        let currentPage = 'dashboard';
        let userAnswers = {}; // Store answers as a map: { questionIndex: 'selectedAnswer' }
        let timerStart = 0;
        let timerInterval = null;
        let timeLimitSeconds = null;
        let userProfile = {
            scores: [],
            achievements: [],
            subjectAccuracy: {},
        };
        let leaderboardData = [];
        let confettiInterval;
        let activeQuizQuestions = []; // New variable to hold the questions for the current quiz
        let quizSettings = {}; // Store all quiz settings

        const motivationalQuotes = [
            "The only way to learn is to keep trying.",
            "Every expert was once a beginner.",
            "Your potential is endless.",
            "Don't stop until you're proud.",
            "Believe you can and you're halfway there.",
        ];

        // Theme colors
        const themes = {
            'default': {
                '--bg': '#F9FAFB', '--text': '#111827', '--card-bg': '#FFFFFF', '--primary': '#4F46E5', '--primary-hover': '#4338CA', '--shadow': '0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1)', '--border-color': '#E5E7EB'
            },
            'blue': {
                '--bg': '#E0F7FA', '--text': '#006064', '--card-bg': '#B3E5FC', '--primary': '#0288D1', '--primary-hover': '#01579B', '--shadow': '0 4px 6px -1px rgb(2 136 209 / 0.3), 0 2px 4px -2px rgb(2 136 209 / 0.2)', '--border-color': '#81D4FA'
            },
            'dark': {
                '--bg': '#1F2937', '--text': '#F9FAFB', '--card-bg': '#374151', '--primary': '#6366F1', '--primary-hover': '#4F46E5', '--shadow': '0 4px 6px -1px rgb(0 0 0 / 0.3), 0 2px 4px -2px rgb(0 0 0 / 0.2)', '--border-color': '#4B5563'
            }
        };

        // Firebase Initialization and Authentication
        async function initFirebase() {
            try {
                if (Object.keys(firebaseConfig).length > 0) {
                    app = initializeApp(firebaseConfig);
                    db = getFirestore(app);
                    auth = getAuth(app);
                    console.log("Firebase initialized.");

                    await new Promise(resolve => {
                        const unsubscribe = onAuthStateChanged(auth, async (user) => {
                            if (user) {
                                userId = user.uid;
                                isAuthReady = true;
                                setupListeners();
                                console.log("User authenticated:", userId);
                            } else {
                                if (initialAuthToken) {
                                    try {
                                        await signInWithCustomToken(auth, initialAuthToken);
                                        userId = auth.currentUser.uid;
                                        isAuthReady = true;
                                        setupListeners();
                                        console.log("Signed in with custom token:", userId);
                                    } catch (error) {
                                        console.error("Error signing in with custom token. Falling back to anonymous auth.", error);
                                        await signInAnonymously(auth);
                                    }
                                } else {
                                    await signInAnonymously(auth);
                                }
                            }
                            unsubscribe();
                            resolve();
                        });
                    });
                } else {
                    console.error("Firebase config is missing. The app will not be able to save or load data.");
                }

            } catch (error) {
                console.error("Firebase init failed:", error);
            }
        }

        // Firestore Listeners
        function setupListeners() {
            // User profile listener
            if (userId) {
                const userProfileDocRef = doc(db, `artifacts/${appId}/users/${userId}/quizData/profile`);
                onSnapshot(userProfileDocRef, (docSnap) => {
                    if (docSnap.exists()) {
                        userProfile = docSnap.data();
                    } else {
                        userProfile = { scores: [], achievements: [], subjectAccuracy: {} };
                    }
                    renderCurrentPage();
                }, (error) => {
                    console.error("Error listening to user profile:", error);
                });
            } else {
                console.log("User ID not available. Cannot set up profile listener.");
            }

            // Leaderboard listener
            const q = query(collection(db, `artifacts/${appId}/public/data/leaderboard`), orderBy("score", "desc"), limit(10));
            onSnapshot(q, (snapshot) => {
                leaderboardData = [];
                snapshot.forEach((doc) => {
                    leaderboardData.push(doc.data());
                });
                renderCurrentPage();
            }, (error) => {
                console.error("Error listening to leaderboard:", error);
            });
        }

        // UI Functions
        function showPage(pageName) {
            currentPage = pageName;
            if (confettiInterval) {
                clearInterval(confettiInterval);
            }
            // Clear any active timers
            if (timerInterval) {
                clearInterval(timerInterval);
                timerInterval = null;
            }
            renderCurrentPage();
        }

        function renderCurrentPage() {
            const appContainer = document.getElementById('app-container');
            const pageTitle = document.getElementById('page-title');
            if (!appContainer || !pageTitle) return;

            // Stop any ongoing confetti effect before rendering new page
            if (confettiInterval) {
                clearInterval(confettiInterval);
                confettiInterval = null;
            }
            
            let content = '';
            let titleText = '';
            let pageClass = 'p-4 sm:p-8 flex-1 flex items-center justify-center';

            switch (currentPage) {
                case 'quiz-setup':
                    content = renderQuizSetupPage();
                    titleText = 'Customize Quiz';
                    break;
                case 'quiz-preview':
                    content = renderQuizPreviewPage();
                    titleText = 'Quiz Confirmation';
                    break;
                case 'quiz':
                    content = renderQuizPage();
                    titleText = 'Quiz';
                    break;
                case 'results':
                    content = renderResultsPage();
                    titleText = 'Results';
                    break;
                case 'dashboard':
                    content = renderDashboardPage();
                    titleText = 'Dashboard';
                    break;
                case 'leaderboard':
                    content = renderLeaderboardPage();
                    titleText = 'Leaderboard';
                    break;
                case 'themes':
                    content = renderThemesPage();
                    titleText = 'Themes';
                    break;
                case 'certificate':
                    content = renderCertificatePage();
                    titleText = 'Certificate';
                    break;
                case 'share':
                    content = renderSharePage();
                    titleText = 'Share Results';
                    break;
                default:
                    content = renderDashboardPage();
                    titleText = 'Dashboard';
            }

            pageTitle.textContent = titleText;
            appContainer.innerHTML = content;
            
            // Handle post-render logic
            handlePageLoad();
            updateSidebar();
        }

        function handlePageLoad() {
            switch(currentPage) {
                case 'quiz-setup':
                    setupQuizOptions();
                    break;
                case 'quiz-preview':
                    document.getElementById('start-quiz-btn').addEventListener('click', () => startQuizFromPreview());
                    break;
                case 'quiz':
                    startTimer();
                    break;
                case 'results':
                    const scorePercentage = (userProfile.lastScore / userProfile.lastQuizQuestionCount) * 100;
                    if (scorePercentage >= 90) {
                         setTimeout(() => {
                             confetti.create(document.getElementById('confetti-canvas'), { resize: true, useAlpha: false })({
                                 particleCount: 100,
                                 spread: 70
                             });
                             playSound(440, 'sine');
                         }, 500);
                     }
                    break;
                case 'share':
                    shareResults();
                    break;
                case 'certificate':
                    generateCertificate();
                    break;
            }
        }
        
        function updateSidebar() {
            const sidebar = document.getElementById('sidebar');
            const userIdDisplay = document.getElementById('user-id-display');
            
            if (userIdDisplay) {
                userIdDisplay.textContent = `User: ${userId ? userId.slice(0, 8) + '...' : 'N/A'}`;
            }

            const navButtons = sidebar.querySelectorAll('button');
            navButtons.forEach(btn => {
                if (btn.dataset.page === currentPage) {
                    btn.classList.add('bg-gray-700');
                    btn.classList.remove('hover:bg-gray-700');
                } else {
                    btn.classList.remove('bg-gray-700');
                    btn.classList.add('hover:bg-gray-700');
                }
            });
        }

        // --- New UI Functions for Quiz Setup ---
        function renderQuizSetupPage() {
            const subjects = Object.keys(quizData).filter(key => quizData[key].type === 'academic').sort();
            const subjectOptions = subjects.map(s => `<option value="${s}">${quizData[s].name}</option>`).join('');

            return `
                <div class="w-full max-w-2xl">
                    <div class="container-card p-6 sm:p-8">
                        <h2 class="text-3xl font-bold mb-6 text-center">Customize Your Quiz</h2>
                        <div class="space-y-6">
                            <div>
                                <label for="quiz-type-select" class="block text-sm font-medium text-gray-700 mb-2">Question Type</label>
                                <select id="quiz-type-select" class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-primary focus:border-primary transition-colors">
                                    <option value="academic">Academic</option>
                                    <option value="admission">Admission</option>
                                </select>
                            </div>
                            <div id="admission-type-container" class="hidden">
                                <label for="admission-type-select" class="block text-sm font-medium text-gray-700 mb-2">Admission Type</label>
                                <select id="admission-type-select" class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-primary focus:border-primary transition-colors">
                                    <option value="">-- Select --</option>
                                    <option value="Engineering">Engineering</option>
                                    <option value="Medical">Medical</option>
                                    <option value="Varsity">Varsity</option>
                                </select>
                            </div>
                            <div id="subject-select-container">
                                <label for="subject-select" class="block text-sm font-medium text-gray-700 mb-2">Select Subject</label>
                                <select id="subject-select" class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-primary focus:border-primary transition-colors">
                                    <option value="">-- All Subjects --</option>
                                    ${subjectOptions}
                                </select>
                            </div>
                            <div id="chapter-select-container" class="hidden">
                                <label for="chapter-select" class="block text-sm font-medium text-gray-700 mb-2">Select Chapter</label>
                                <select id="chapter-select" class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-primary focus:border-primary transition-colors">
                                    <option value="">-- All Chapters --</option>
                                </select>
                            </div>
                            <div>
                                <label for="num-questions-input" class="block text-sm font-medium text-gray-700 mb-2">Number of Questions (1-50)</label>
                                <input type="number" id="num-questions-input" min="1" max="50" value="10" class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-primary focus:border-primary transition-colors">
                            </div>
                            <div>
                                <label for="time-limit-input" class="block text-sm font-medium text-gray-700 mb-2">Time Limit (in minutes)</label>
                                <input type="number" id="time-limit-input" min="0" value="0" placeholder="0 = No limit" class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-primary focus:border-primary transition-colors">
                            </div>
                            <div class="flex items-center">
                                <input type="checkbox" id="negative-marking-checkbox" class="form-checkbox text-primary-500 rounded focus:ring-primary-500">
                                <label for="negative-marking-checkbox" class="ml-2 block text-sm font-medium text-gray-700">Enable Negative Marking (-0.25 per wrong answer)</label>
                            </div>
                        </div>
                        <div class="mt-8 text-center">
                            <button id="preview-quiz-btn" class="btn-primary w-full max-w-xs">Preview & Start Quiz</button>
                        </div>
                    </div>
                </div>
            `;
        }
        
        function renderQuizPreviewPage() {
            return `
                <div class="w-full max-w-2xl">
                    <div class="container-card p-6 sm:p-8 text-center">
                        <h2 class="text-3xl font-bold mb-6">Confirm Quiz Settings</h2>
                        <div class="text-left space-y-4 mb-8">
                            <p class="text-lg"><strong class="font-semibold">Quiz Type:</strong> <span id="preview-quiz-type"></span></p>
                            <p class="text-lg hidden" id="preview-admission-type-container"><strong class="font-semibold">Admission Type:</strong> <span id="preview-admission-type"></span></p>
                            <p class="text-lg"><strong class="font-semibold">Subject:</strong> <span id="preview-subject"></span></p>
                            <p class="text-lg hidden" id="preview-chapter-container"><strong class="font-semibold">Chapter:</strong> <span id="preview-chapter"></span></p>
                            <p class="text-lg"><strong class="font-semibold">Number of Questions:</strong> <span id="preview-num-questions"></span></p>
                            <p class="text-lg"><strong class="font-semibold">Time Limit:</strong> <span id="preview-time-limit"></span></p>
                            <p class="text-lg"><strong class="font-semibold">Negative Marking:</strong> <span id="preview-negative-marking"></span></p>
                        </div>
                        <div class="flex flex-col sm:flex-row justify-center space-y-4 sm:space-y-0 sm:space-x-4">
                            <button id="start-quiz-btn" class="btn-primary w-full sm:w-auto">Start Quiz</button>
                            <button data-page="quiz-setup" class="w-full sm:w-auto p-4 font-semibold text-sm rounded-full text-gray-700 bg-gray-200 hover:bg-gray-300 transition-colors">Edit Settings</button>
                        </div>
                    </div>
                </div>
            `;
        }

        function setupQuizOptions() {
            const previewBtn = document.getElementById('preview-quiz-btn');
            const quizTypeSelect = document.getElementById('quiz-type-select');
            const admissionTypeContainer = document.getElementById('admission-type-container');
            const admissionTypeSelect = document.getElementById('admission-type-select');
            const subjectSelectContainer = document.getElementById('subject-select-container');
            const subjectSelect = document.getElementById('subject-select');
            const chapterSelectContainer = document.getElementById('chapter-select-container');
            const chapterSelect = document.getElementById('chapter-select');

            // Function to populate subject and chapter dropdowns
            function populateDropdowns() {
                const selectedQuizType = quizTypeSelect.value;
                const subjects = Object.keys(quizData).filter(key => quizData[key].type === selectedQuizType).sort();
                
                subjectSelectContainer.classList.remove('hidden');
                subjectSelect.innerHTML = `<option value="">-- All Subjects --</option>` + subjects.map(s => `<option value="${s}">${quizData[s].name}</option>`).join('');
                chapterSelectContainer.classList.add('hidden');
            }

            quizTypeSelect.addEventListener('change', (e) => {
                const selectedType = e.target.value;
                if (selectedType === 'admission') {
                    admissionTypeContainer.classList.remove('hidden');
                    subjectSelectContainer.classList.add('hidden');
                    chapterSelectContainer.classList.add('hidden');
                } else {
                    admissionTypeContainer.classList.add('hidden');
                    populateDropdowns();
                }
            });

            admissionTypeSelect.addEventListener('change', (e) => {
                const selectedAdmissionType = e.target.value;
                if (selectedAdmissionType) {
                    const subjects = Object.keys(quizData).filter(key => quizData[key].admissionType === selectedAdmissionType);
                    subjectSelect.innerHTML = `<option value="">-- All Subjects --</option>` + subjects.map(s => `<option value="${s}">${quizData[s].name}</option>`).join('');
                    subjectSelectContainer.classList.remove('hidden');
                } else {
                    subjectSelectContainer.classList.add('hidden');
                }
            });

            subjectSelect.addEventListener('change', (e) => {
                const selectedSubject = e.target.value;
                if (selectedSubject && quizData[selectedSubject] && quizData[selectedSubject].chapters) {
                    const chapters = Object.keys(quizData[selectedSubject].chapters);
                    chapterSelect.innerHTML = `<option value="">-- All Chapters --</option>` + chapters.map(c => `<option value="${c}">${c}</option>`).join('');
                    chapterSelectContainer.classList.remove('hidden');
                } else {
                    chapterSelectContainer.classList.add('hidden');
                }
            });

            if (previewBtn) {
                previewBtn.addEventListener('click', () => {
                    // Get all settings from the form
                    const quizType = quizTypeSelect.value;
                    const admissionType = admissionTypeSelect.value;
                    const subject = subjectSelect.value;
                    const chapter = chapterSelect.value;
                    const numQuestions = parseInt(document.getElementById('num-questions-input').value, 10);
                    const timeLimitMinutes = parseInt(document.getElementById('time-limit-input').value, 10);
                    const negativeMarking = document.getElementById('negative-marking-checkbox').checked;

                    // Store settings in a global object
                    quizSettings = {
                        quizType,
                        admissionType,
                        subject,
                        chapter,
                        numQuestions: numQuestions > 0 ? Math.min(numQuestions, 50) : 10,
                        timeLimitSeconds: timeLimitMinutes * 60,
                        negativeMarking
                    };

                    // Show the preview page
                    showPage('quiz-preview');
                    
                    // Populate the preview page
                    document.getElementById('preview-quiz-type').textContent = quizType.toUpperCase();
                    
                    const admissionTypeContainer = document.getElementById('preview-admission-type-container');
                    if (quizType === 'admission') {
                        admissionTypeContainer.classList.remove('hidden');
                        document.getElementById('preview-admission-type').textContent = admissionType || 'All';
                    } else {
                        admissionTypeContainer.classList.add('hidden');
                    }

                    document.getElementById('preview-subject').textContent = quizData[subject]?.name || 'All Subjects';
                    
                    const chapterContainer = document.getElementById('preview-chapter-container');
                    if (chapter) {
                        chapterContainer.classList.remove('hidden');
                        document.getElementById('preview-chapter').textContent = chapter;
                    } else {
                        chapterContainer.classList.add('hidden');
                    }
                    
                    document.getElementById('preview-num-questions').textContent = quizSettings.numQuestions;
                    document.getElementById('preview-time-limit').textContent = quizSettings.timeLimitSeconds > 0 ? `${quizSettings.timeLimitSeconds / 60} minutes` : 'No Limit';
                    document.getElementById('preview-negative-marking').textContent = quizSettings.negativeMarking ? 'Yes' : 'No';
                });
            }

            // Initial population
            populateDropdowns();
        }
        
        function startQuizFromPreview() {
            // Find the questions based on the stored settings
            let questionsToDrawFrom = [];
            const { quizType, admissionType, subject, chapter, numQuestions } = quizSettings;

            if (quizType === 'academic') {
                if (!subject) {
                    Object.keys(quizData).filter(key => quizData[key].type === 'academic').forEach(subjKey => {
                        for (const chapKey in quizData[subjKey].chapters) {
                            questionsToDrawFrom = questionsToDrawFrom.concat(quizData[subjKey].chapters[chapKey]);
                        }
                    });
                } else if (!chapter) {
                    for (const chapKey in quizData[subject].chapters) {
                        questionsToDrawFrom = questionsToDrawFrom.concat(quizData[subject].chapters[chapKey]);
                    }
                } else {
                    questionsToDrawFrom = quizData[subject].chapters[chapter];
                }
            } else { // admission type
                if (!admissionType) {
                     Object.keys(quizData).filter(key => quizData[key].type === 'admission').forEach(subjKey => {
                        for (const chapKey in quizData[subjKey].chapters) {
                            questionsToDrawFrom = questionsToDrawFrom.concat(quizData[subjKey].chapters[chapKey]);
                        }
                    });
                } else {
                    const admissionSubjects = Object.keys(quizData).filter(key => quizData[key].admissionType === admissionType);
                    admissionSubjects.forEach(subjKey => {
                         for (const chapKey in quizData[subjKey].chapters) {
                            questionsToDrawFrom = questionsToDrawFrom.concat(quizData[subjKey].chapters[chapKey]);
                        }
                    });
                }
            }

            // Shuffle and limit questions
            activeQuizQuestions = questionsToDrawFrom.sort(() => 0.5 - Math.random()).slice(0, numQuestions);
            
            // The time limit and negative marking are already set in quizSettings. No reassignment is needed.
            userAnswers = {};
            showPage('quiz');
        }

        // Dynamic HTML generation functions
        function renderQuizPage() {
            let questionsHTML = '';
            activeQuizQuestions.forEach((q, index) => {
                questionsHTML += `
                    <div class="mb-8 p-6 bg-gray-50 rounded-lg shadow-sm">
                        <p class="text-sm font-medium text-gray-500 mb-2">Question ${index + 1} of ${activeQuizQuestions.length}</p>
                        <h3 class="text-xl font-semibold mb-4 leading-relaxed">${q.question}</h3>
                        <div class="space-y-3" id="q-${index}-answers">
                            ${q.answers.map(answer => `
                                <label class="flex items-center space-x-3 p-3 bg-white rounded-lg border border-gray-200 cursor-pointer hover:bg-gray-100 transition-colors">
                                    <input type="radio" name="question-${index}" value="${answer}" class="form-radio text-primary-500">
                                    <span class="text-gray-700">${answer}</span>
                                </label>
                            `).join('')}
                        </div>
                    </div>
                `;
            });

            return `
                <div class="w-full max-w-3xl flex-col">
                    <div id="quiz-header" class="flex justify-between items-center mb-6 p-4 rounded-lg bg-gray-100 shadow-sm">
                        <p class="font-bold">Time Remaining:</p>
                        <span id="timer" class="text-lg font-bold"></span>
                    </div>
                    <form id="quiz-form" class="space-y-8">
                        ${questionsHTML}
                        <div class="text-center">
                            <button type="submit" class="btn-primary w-full max-w-xs">Submit Quiz</button>
                        </div>
                    </form>
                </div>
            `;
        }
        
        function renderResultsPage() {
            return `
                <div class="w-full max-w-2xl">
                    <div class="container-card p-6 sm:p-8 text-center relative">
                        <canvas id="confetti-canvas" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 10;"></canvas>
                        <h2 class="text-4xl sm:text-5xl font-extrabold text-green-600 mb-4">Quiz Complete!</h2>
                        <p id="final-score" class="text-3xl font-bold mb-2">Your score: ${userProfile.lastScore} / ${userProfile.lastQuizQuestionCount}</p>
                        <p id="score-percentage" class="text-lg text-gray-700 mb-2">Accuracy: ${(userProfile.lastScore / userProfile.lastQuizQuestionCount) * 100}%</p>
                        <p id="time-taken" class="text-sm text-gray-500 mb-8">Time Taken: ${userProfile.lastTimeTaken} seconds</p>
                        <div class="space-y-4">
                            <button data-page="dashboard" class="btn-primary w-full">View Dashboard</button>
                            <button data-page="share" class="w-full p-4 font-semibold text-sm rounded-full text-gray-700 bg-gray-200 hover:bg-gray-300 transition-colors">Share Results</button>
                        </div>
                    </div>
                </div>
            `;
        }
        
        function renderDashboardPage() {
            let lastScoreHTML = `<p class="text-lg text-gray-500">Complete a quiz to see your progress here!</p>`;
            let quizzesCompletedHTML = '';
            let bestSubjectHTML = '';

            if (userProfile && userProfile.scores && userProfile.scores.length > 0) {
                lastScoreHTML = `<p class="text-sm text-gray-500">Last Score</p><p class="text-3xl font-bold text-gray-800">${userProfile.lastScore} / ${userProfile.lastQuizQuestionCount || Object.values(quizData).flatMap(s => s.chapters).flatMap(c => Object.values(c)).flat().length}</p>`;
                quizzesCompletedHTML = `<p class="text-sm text-gray-500">Quizzes Completed</p><p class="text-3xl font-bold text-gray-800">${userProfile.scores.length}</p>`;
                
                let bestSubject = 'N/A';
                let highestAccuracy = 0;
                for (const subject in userProfile.subjectAccuracy) {
                    const { correct, total } = userProfile.subjectAccuracy[subject];
                    const accuracy = total > 0 ? (correct / total) : 0;
                    if (accuracy > highestAccuracy) {
                        highestAccuracy = accuracy;
                        bestSubject = subject;
                    }
                }
                bestSubjectHTML = `<p class="text-sm text-gray-500">Best Subject</p><p class="text-xl font-bold text-gray-800">${bestSubject} (${(highestAccuracy * 100).toFixed(0)}%)</p>`;
            }
            
            let performanceBreakdownHTML = '';
            let totalCorrect = 0;
            let totalQuestions = 0;
            for (const subject in userProfile.subjectAccuracy) {
                const { correct, total } = userProfile.subjectAccuracy[subject];
                totalCorrect += correct;
                totalQuestions += total;
                const percentage = total > 0 ? ((correct / total) * 100).toFixed(0) : 0;
                performanceBreakdownHTML += `<p class="text-gray-700">${quizData[subject].name}: ${percentage}%</p>`;
            }
            const overallAccuracy = totalQuestions > 0 ? ((totalCorrect / totalQuestions) * 100).toFixed(0) : 0;
            performanceBreakdownHTML += `<div class="mt-4 border-t pt-4"><p class="font-bold">Overall Accuracy: ${overallAccuracy}%</p></div>`;

            let progressTrackingHTML = '';
            if (userProfile.scores && userProfile.scores.length > 0) {
                userProfile.scores.forEach((s, i) => {
                    const scorePercentage = (s.score / s.questionCount) * 100;
                    progressTrackingHTML += `
                        <div class="mb-2 p-3 bg-gray-50 rounded-lg border-l-4 border-gray-200">
                            <p class="font-semibold text-gray-800">Quiz ${i + 1} on ${new Date(s.date).toLocaleDateString()}</p>
                            <p class="text-sm text-gray-600">Score: ${s.score} / ${s.questionCount} (${scorePercentage.toFixed(0)}%)</p>
                        </div>
                    `;
                });
            } else {
                 progressTrackingHTML += `<p class="text-gray-600">No quizzes completed yet.</p>`;
            }

            let achievementsHTML = '';
            const unlockedAchievements = achievements.filter(ach => userProfile.achievements.includes(ach.id));
            if (unlockedAchievements.length > 0) {
                unlockedAchievements.forEach(ach => {
                    achievementsHTML += `<div class="bg-yellow-100 p-3 rounded-lg flex items-center mb-2"><span class="mr-2 text-yellow-500">🏆</span><div><div class="font-bold">${ach.name}</div><div class="text-sm text-gray-600">${ach.description}</div></div></div>`;
                });
            } else {
                achievementsHTML += `<p class="text-gray-600">No achievements unlocked yet.</p>`;
            }
            
            const randomQuote = motivationalQuotes[Math.floor(Math.random() * motivationalQuotes.length)];


            return `
                <div class="w-full max-w-2xl text-center">
                    <div class="container-card p-8 sm:p-12">
                        <h1 class="text-4xl sm:text-5xl font-extrabold mb-4 leading-tight">Your Dashboard</h1>
                        <p class="text-lg text-gray-600 mb-8">View your progress and achievements here.</p>
                        <div class="space-y-4">
                            <button data-page="quiz-setup" class="btn-primary w-full">Start New Quiz</button>
                            <button data-page="leaderboard" class="w-full p-4 font-semibold text-sm rounded-full text-gray-700 bg-gray-200 hover:bg-gray-300 transition-colors">View Leaderboard</button>
                            <button data-page="themes" class="w-full p-4 font-semibold text-sm rounded-full text-gray-700 bg-gray-200 hover:bg-gray-300 transition-colors">Customize Themes</button>
                        </div>
                    </div>

                    <div class="mt-8 grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <div class="container-card p-6 flex flex-col items-center justify-center">
                            <div class="text-center" id="last-score-display">${lastScoreHTML}</div>
                        </div>
                        <div class="container-card p-6 flex flex-col items-center justify-center">
                            <div class="text-center" id="quizzes-completed-display">${quizzesCompletedHTML}</div>
                        </div>
                        <div class="container-card p-6 col-span-1 sm:col-span-2 flex flex-col items-center justify-center">
                            <div class="text-center" id="best-subject-display">${bestSubjectHTML}</div>
                        </div>
                        <div class="container-card p-6 col-span-1 sm:col-span-2 flex flex-col items-center justify-center">
                            <p id="motivational-quote" class="text-lg italic text-gray-600">${randomQuote}</p>
                        </div>
                        <div class="container-card p-6 col-span-1 sm:col-span-2">
                            <h3 class="text-xl font-semibold mb-2">Performance Breakdown</h3>
                            <div id="performance-breakdown">${performanceBreakdownHTML}</div>
                        </div>
                        <div class="container-card p-6 col-span-1 sm:col-span-2">
                            <h3 class="text-xl font-semibold mb-2">Achievements</h3>
                            <div id="achievements-list">${achievementsHTML}</div>
                        </div>
                        <div class="container-card p-6 col-span-1 sm:col-span-2">
                            <h3 class="text-xl font-semibold mb-4">Exam History</h3>
                            <div id="progress-tracking">${progressTrackingHTML}</div>
                        </div>
                         <div class="space-y-4 col-span-1 sm:col-span-2">
                            <button data-page="certificate" class="w-full p-4 font-semibold text-sm rounded-full text-gray-700 bg-gray-200 hover:bg-gray-300 transition-colors">Generate Certificate</button>
                        </div>
                    </div>
                </div>
            `;
        }
        
        function renderLeaderboardPage() {
             let leaderboardListHTML = '';
             if (leaderboardData && leaderboardData.length > 0) {
                 leaderboardData.forEach((entry, index) => {
                     const isCurrentUser = userId && entry.userId === userId;
                     const rowClass = isCurrentUser ? 'bg-indigo-100 font-bold' : 'bg-gray-50';
                     leaderboardListHTML += `<div class="p-4 ${rowClass} rounded-lg shadow-sm mb-2 flex justify-between items-center"><div><span class="font-bold">${index + 1}.</span> User ${entry.userId.slice(0, 5)}...</div><div>Score: ${entry.score}</div></div>`;
                 });
             } else {
                 leaderboardListHTML = `<p class="text-center text-gray-500">No scores on the leaderboard yet. Be the first!</p>`;
             }
            
             const userEntry = leaderboardData.find(entry => entry.userId === userId);
             const userRankHTML = userEntry ? `<p class="text-center text-gray-700 font-semibold">Your rank: ${leaderboardData.findIndex(entry => entry.userId === userId) + 1}</p>` : `<p class="text-center text-gray-700">Complete a quiz to see your rank.</p>`;
            
            return `
                <div class="w-full max-w-2xl">
                    <div class="container-card p-6 sm:p-8">
                        <h2 class="text-3xl font-bold mb-6 text-center">Leaderboard</h2>
                        <div id="user-rank" class="mb-6 p-4 bg-gray-100 rounded-lg">${userRankHTML}</div>
                        <div id="leaderboard-list">${leaderboardListHTML}</div>
                        <div class="mt-8 text-center">
                            <button data-page="dashboard" class="w-full max-w-xs p-4 font-semibold text-sm rounded-full text-gray-700 bg-gray-200 hover:bg-gray-300 transition-colors">Go Dashboard</button>
                        </div>
                    </div>
                </div>
            `;
        }
        
        function renderThemesPage() {
            return `
                <div class="w-full max-w-2xl">
                    <div class="container-card p-6 sm:p-8 text-center">
                        <h2 class="text-3xl font-bold mb-6">Choose Your Theme</h2>
                        <div class="flex justify-center space-x-6 mb-8">
                            <button id="default-theme-btn" class="theme-btn bg-white" style="box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1)"></button>
                            <button id="blue-theme-btn" class="theme-btn bg-sky-200" style="box-shadow: 0 4px 6px -1px rgb(2 136 209 / 0.3), 0 2px 4px -2px rgb(2 136 209 / 0.2)"></button>
                            <button id="dark-theme-btn" class="theme-btn bg-gray-800" style="box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.3), 0 2px 4px -2px rgb(0 0 0 / 0.2)"></button>
                        </div>
                        <button data-page="dashboard" class="btn-primary w-full max-w-xs">Go Dashboard</button>
                    </div>
                </div>
            `;
        }

        function renderSharePage() {
            return `
                <div class="w-full max-w-2xl">
                    <div class="container-card p-6 sm:p-8 text-center">
                        <h2 class="text-3xl font-bold mb-6">Share Your Results</h2>
                        <p class="text-gray-600 mb-4">Your shareable image is ready. Right-click to save or click the button below to download.</p>
                        <div id="shareable-card" class="bg-white p-6 rounded-lg shadow-lg hidden">
                            <h3 class="text-2xl font-bold mb-2">Quiz Master Result</h3>
                            <p class="text-lg font-medium text-gray-700">User: ${userId ? userId.slice(0, 8) + '...' : 'N/A'}</p>
                            <p class="text-4xl font-extrabold text-green-600 mt-4">${userProfile.lastScore || 'N/A'} / ${userProfile.lastQuizQuestionCount}</p>
                            <p class="text-sm font-medium text-gray-500">Completed on ${new Date().toLocaleDateString()}</p>
                        </div>
                        <img id="share-image" class="w-full rounded-lg mb-6 border border-gray-200" alt="Shareable Quiz Result">
                        <button id="copy-share-image" class="btn-primary w-full mb-4">Download Image</button>
                        <button data-page="dashboard" class="w-full p-4 font-semibold text-sm rounded-full text-gray-700 bg-gray-200 hover:bg-gray-300 transition-colors">Go Dashboard</button>
                    </div>
                </div>
            `;
        }

        function renderCertificatePage() {
            return `
                <div class="w-full max-w-4xl">
                    <div class="container-card p-4 sm:p-8">
                        <h2 class="text-3xl font-bold mb-6 text-center">Your Certificate</h2>
                        <iframe id="certificate-viewer" class="w-full h-[60vh] sm:h-[80vh] border-2 border-gray-300 rounded-lg mb-6"></iframe>
                        <div class="flex justify-center">
                            <button data-page="dashboard" class="btn-primary max-w-xs">Go Dashboard</button>
                        </div>
                    </div>
                </div>
            `;
        }


        function playSound(frequency, type) {
            const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            const oscillator = audioCtx.createOscillator();
            const gainNode = audioCtx.createGain();

            oscillator.type = type;
            oscillator.frequency.setValueAtTime(frequency, audioCtx.currentTime);
            gainNode.gain.setValueAtTime(0.5, audioCtx.currentTime);

            oscillator.connect(gainNode);
            gainNode.connect(audioCtx.destination);
            oscillator.start();
            oscillator.stop(audioCtx.currentTime + 0.3);
        }

        // --- Core Quiz Logic ---
        function startCustomQuiz(settings) {
            const { quizType, admissionType, subject, chapter, numQuestions, timeLimitSeconds, negativeMarking } = settings;
            let questionsToDrawFrom = [];
            
            if (quizType === 'academic') {
                if (subject && quizData[subject]) {
                    if (chapter) {
                        questionsToDrawFrom = quizData[subject].chapters[chapter] || [];
                    } else {
                        questionsToDrawFrom = Object.values(quizData[subject].chapters).flat();
                    }
                } else {
                    Object.keys(quizData).filter(key => quizData[key].type === 'academic').forEach(subjKey => {
                        questionsToDrawFrom = questionsToDrawFrom.concat(Object.values(quizData[subjKey].chapters).flat());
                    });
                }
            } else { // admission type
                 if (admissionType) {
                    const subjects = Object.keys(quizData).filter(key => quizData[key].admissionType === admissionType);
                    subjects.forEach(subjKey => {
                         questionsToDrawFrom = questionsToDrawFrom.concat(Object.values(quizData[subjKey].chapters).flat());
                    });
                } else { // all admission
                    Object.keys(quizData).filter(key => quizData[key].type === 'admission').forEach(subjKey => {
                         questionsToDrawFrom = questionsToDrawFrom.concat(Object.values(quizData[subjKey].chapters).flat());
                    });
                }
            }
            
            // Check if enough questions are available
            const questionsCount = Math.min(numQuestions, questionsToDrawFrom.length);
            activeQuizQuestions = questionsToDrawFrom.sort(() => 0.5 - Math.random()).slice(0, questionsCount);
            
            // Set time limit and reset answers
            quizSettings.timeLimitSeconds = timeLimitSeconds;
            quizSettings.negativeMarking = negativeMarking;
            userAnswers = {};
            showPage('quiz');
        }

        function startTimer() {
            const timerElement = document.getElementById('timer');
            const quizForm = document.getElementById('quiz-form');
            if (!timerElement || !quizForm) return;

            // Add submit event listener for the form
            quizForm.addEventListener('submit', (e) => {
                e.preventDefault();
                submitQuiz();
            });

            // Start the timer
            timerStart = Date.now();
            let timeRemaining = quizSettings.timeLimitSeconds;

            if (timeRemaining > 0) {
                timerElement.textContent = `${Math.floor(timeRemaining/60)}m ${timeRemaining % 60}s`;
                timerInterval = setInterval(() => {
                    timeRemaining--;
                    timerElement.textContent = `${Math.floor(timeRemaining/60)}m ${timeRemaining % 60}s`;
                    if (timeRemaining <= 0) {
                        clearInterval(timerInterval);
                        timerInterval = null;
                        submitQuiz();
                    }
                }, 1000);
            } else {
                timerElement.textContent = 'No time limit';
            }
        }
        
        function submitQuiz() {
            // Stop the timer
            if (timerInterval) {
                clearInterval(timerInterval);
                timerInterval = null;
            }

            const timeTaken = Math.round((Date.now() - timerStart) / 1000);
            let score = 0;
            let incorrectCount = 0;
            const subjectAccuracy = {};
            
            // Collect answers from the form and calculate score
            activeQuizQuestions.forEach((q, index) => {
                const radios = document.getElementsByName(`question-${index}`);
                let userAnswer = null;
                for (const radio of radios) {
                    if (radio.checked) {
                        userAnswer = radio.value;
                        break;
                    }
                }
                
                let isCorrect = false;
                if (userAnswer) {
                    userAnswers[index] = userAnswer;
                    isCorrect = userAnswer === q.correct;
                    if (isCorrect) {
                        score++;
                    } else {
                        incorrectCount++;
                    }
                }
                
                const subjectKey = Object.keys(quizData).find(subjKey => 
                    Object.values(quizData[subjKey].chapters).flat().some(item => item.question === q.question)
                );
                
                if (subjectKey) {
                    if (!subjectAccuracy[subjectKey]) {
                        subjectAccuracy[subjectKey] = { correct: 0, total: 0 };
                    }
                    if (isCorrect) {
                        subjectAccuracy[subjectKey].correct++;
                    }
                    subjectAccuracy[subjectKey].total++;
                }
            });

            if (quizSettings.negativeMarking) {
                 score = Math.max(0, score - (incorrectCount * 0.25));
            }
            
            saveQuizResult(score, subjectAccuracy, timeTaken, activeQuizQuestions.length);
            showPage('results');
        }

        // Data Storage and Retrieval
        async function saveQuizResult(score, subjectAccuracy, timeTaken, questionCount) {
            if (!isAuthReady) {
                console.error("Authentication not ready. Cannot save data.");
                return;
            }
            const userProfileDocRef = doc(db, `artifacts/${appId}/users/${userId}/quizData/profile`);
            const leaderboardDocRef = doc(db, `artifacts/${appId}/public/data/leaderboard`, userId);

            // Update user profile
            const newScores = userProfile.scores || [];
            newScores.push({ score, date: new Date().toISOString(), questionCount });
            const newAchievements = checkAchievements(userProfile.achievements || [], score, newScores.length, timeTaken);
            const combinedSubjectAccuracy = {};
            for (const subject in subjectAccuracy) {
                const prev = userProfile.subjectAccuracy[subject] || { correct: 0, total: 0 };
                combinedSubjectAccuracy[subject] = {
                    correct: prev.correct + (subjectAccuracy[subject]?.correct || 0),
                    total: prev.total + (subjectAccuracy[subject]?.total || 0)
                };
            }

            await setDoc(userProfileDocRef, {
                scores: newScores,
                subjectAccuracy: combinedSubjectAccuracy,
                achievements: newAchievements,
                lastScore: score,
                lastScoreDate: new Date().toISOString(),
                lastQuizQuestionCount: questionCount,
                lastTimeTaken: timeTaken,
            });

            // Update leaderboard
            await setDoc(leaderboardDocRef, {
                userId: userId,
                score: score,
                timestamp: new Date().toISOString()
            });
        }

        const achievements = [
            { id: 'perfect-score', name: 'Perfect Score', description: 'Get a perfect score on a quiz.', condition: (score) => score === activeQuizQuestions.length },
            { id: 'consistent-learner', name: 'Consistent Learner', description: 'Complete 3 quizzes.', condition: (quizCount) => quizCount >= 3 },
            { id: 'fast-solver', name: 'Fast Solver', description: 'Complete a quiz in under 30 seconds.', condition: (time) => time < 30 },
        ];

        function checkAchievements(unlocked, lastScore, quizCount, totalTime) {
            let updated = [...unlocked];
            achievements.forEach(ach => {
                if (!updated.includes(ach.id)) {
                    if (ach.id === 'perfect-score' && ach.condition(lastScore)) {
                        updated.push(ach.id);
                    } else if (ach.id === 'consistent-learner' && ach.condition(quizCount)) {
                        updated.push(ach.id);
                    } else if (ach.id === 'fast-solver' && ach.condition(totalTime)) {
                        updated.push(ach.id);
                    }
                }
            });
            return updated;
        }

        // Theme switching
        function applyTheme(themeName) {
            const theme = themes[themeName];
            const root = document.documentElement;
            for (const [key, value] of Object.entries(theme)) {
                root.style.setProperty(key, value);
            }
            localStorage.setItem('theme', themeName);
        }

        function loadTheme() {
            const savedTheme = localStorage.getItem('theme') || 'default';
            applyTheme(savedTheme);
        }

        // Share functionality
        async function shareResults() {
            const shareableCard = document.getElementById('shareable-card');
            if (shareableCard) {
                shareableCard.style.display = 'block';

                const canvas = await html2canvas(shareableCard, { scale: 2 });
                const imgUrl = canvas.toDataURL('image/png');
                document.getElementById('share-image').src = imgUrl;
                shareableCard.style.display = 'none';

                document.getElementById('copy-share-image').onclick = () => {
                    const dataUrl = imgUrl.replace('image/png', 'image/octet-stream');
                    const link = document.createElement('a');
                    link.href = dataUrl;
                    link.download = 'quiz_result.png';
                    link.click();
                };
            }
        }

        // Certificate Generator
        function generateCertificate() {
            const { jsPDF } = window.jspdf;
            const doc = new jsPDF({
                orientation: 'landscape',
                unit: 'pt',
                format: 'a4'
            });

            const userFinalScore = userProfile.lastScore || 0;
            const userCompletionDate = new Date().toLocaleDateString();

            doc.setFillColor(255, 255, 255);
            doc.rect(0, 0, 842, 595, 'F');
            doc.setFontSize(40);
            doc.text("Certificate of Completion", 421, 100, null, null, "center");
            doc.setFontSize(24);
            doc.text("This certifies that", 421, 160, null, null, "center");
            doc.setFontSize(36);
            doc.text(`User ${userId.slice(0, 8)}...`, 421, 220, null, null, "center");
            doc.setFontSize(24);
            doc.text("has successfully completed the Quiz Master Challenge with a score of:", 421, 280, null, null, "center");
            doc.setFontSize(48);
            doc.setTextColor(0, 102, 204);
            doc.text(`${userFinalScore} / ${userProfile.lastQuizQuestionCount || Object.values(quizData).flatMap(s => s.chapters).flatMap(c => Object.values(c)).flat().length}`, 421, 350, null, null, "center");
            doc.setFontSize(18);
            doc.setTextColor(0, 0, 0);
            doc.text(`On: ${userCompletionDate}`, 421, 420, null, null, "center");

            const certificateUrl = doc.output('datauristring');
            document.getElementById('certificate-viewer').src = certificateUrl;
        }

        // Initial setup
        document.addEventListener('DOMContentLoaded', () => {
            loadTheme();
            initFirebase().then(() => {
                renderCurrentPage();
            });
        });

        // Event delegation for navigation buttons
        document.body.addEventListener('click', (e) => {
            const button = e.target.closest('[data-page]');
            if (button) {
                showPage(button.dataset.page);
            }
            if (e.target.id === 'default-theme-btn') {
                applyTheme('default');
            } else if (e.target.id === 'blue-theme-btn') {
                applyTheme('blue');
            } else if (e.target.id === 'dark-theme-btn') {
                applyTheme('dark');
            }
        });
    </script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg);
            color: var(--text);
            transition: background-color 0.3s, color 0.3s;
        }
        .container-card {
            background-color: var(--card-bg);
            box-shadow: var(--shadow);
            border-radius: 12px;
            border: 1px solid var(--border-color);
        }
        .btn-primary {
            background-color: var(--primary);
            color: white;
            padding: 1rem 2rem;
            border-radius: 9999px;
            font-weight: 600;
            transition-property: background-color, border-color, color, fill, stroke, opacity, box-shadow, transform;
            transition-duration: .3s;
        }
        .btn-primary:hover {
            background-color: var(--primary-hover);
            transform: translateY(-2px);
        }
        .theme-btn {
            width: 48px;
            height: 48px;
            border-radius: 50%;
            border: 2px solid transparent;
            cursor: pointer;
            transition: border-color 0.3s;
        }
        .theme-btn:hover {
            border-color: var(--primary);
        }
    </style>
</head>
<body class="flex min-h-screen">
    <nav id="sidebar" class="w-64 bg-gray-900 text-white p-6 space-y-6 flex-shrink-0">
        <h1 class="text-2xl font-bold mb-4">Quiz Master</h1>
        <p id="user-id-display" class="text-sm text-gray-400 mb-6"></p>
        <div class="space-y-2">
            <button data-page="dashboard" class="w-full text-left p-3 rounded-lg font-medium transition-colors hover:bg-gray-700">Dashboard</button>
            <button data-page="quiz-setup" class="w-full text-left p-3 rounded-lg font-medium transition-colors hover:bg-gray-700">Start Quiz</button>
            <button data-page="leaderboard" class="w-full text-left p-3 rounded-lg font-medium transition-colors hover:bg-gray-700">Leaderboard</button>
            <button data-page="themes" class="w-full text-left p-3 rounded-lg font-medium transition-colors hover:bg-gray-700">Themes</button>
        </div>
    </nav>
    
    <main class="flex-1 p-8 overflow-auto flex flex-col items-center">
        <h1 id="page-title" class="text-4xl font-extrabold mb-8"></h1>
        <div id="app-container" class="w-full flex-1 flex flex-col items-center justify-center">
            <!-- Page content will be dynamically loaded here -->
        </div>
    </main>
</body>
</html>

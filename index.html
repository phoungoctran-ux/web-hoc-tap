import React, { useState, useEffect, useRef } from 'react';
import { 
  Play, Pause, RotateCcw, Droplet, Plus, Check, Trash2, 
  BookOpen, Heart, Activity, BarChart2, CheckSquare, PlusCircle, 
  ChevronRight, Star, Volume2, VolumeX, Info, ShieldAlert,
  Lock, Unlock, Pin, RefreshCw, Trophy, Flame, Zap, Sparkles, Send, HelpCircle, 
  MessageSquare, Book, Camera, Image as ImageIcon, Calendar, Trash, Edit3, Globe, Map, LogOut, Key, FileText, Database, ShieldCheck, Link as LinkIcon, ExternalLink, FileUp, Dumbbell, Smile
} from 'lucide-react';

import { initializeApp } from "firebase/app";
import { getFirestore, doc, setDoc, getDoc } from "firebase/firestore";

// Cấu hình Sandbox mặc định (Nếu không có key cá nhân, app sẽ chạy Offline Local siêu mượt)
const DEFAULT_FIREBASE_CONFIG = {
  apiKey: "AIzaSyAs8G3P-sandbox-config-key-for-snoopy-app",
  authDomain: "snoopy-study-dash-demo.firebaseapp.com",
  projectId: "snoopy-study-dash-demo",
  storageBucket: "snoopy-study-dash-demo.appspot.com",
  messagingSenderId: "1234567890",
  appId: "1:1234567890:web:abcdefg12345"
};

async function hashPasscode(passcode) {
  if (!passcode) return '';
  const msgUint8 = new TextEncoder().encode(passcode.trim().toLowerCase());
  const hashBuffer = await crypto.subtle.digest('SHA-256', msgUint8);
  const hashArray = Array.from(new Uint8Array(hashBuffer));
  return hashArray.map(b => b.toString(16).padStart(2, '0')).join('');
}

const playAudioFeedback = (type, isMuted) => {
  if (isMuted) return;
  try {
    const AudioContext = window.AudioContext || window.webkitAudioContext;
    if (!AudioContext) return;
    const ctx = new AudioContext();
    const osc = ctx.createOscillator();
    const gain = ctx.createGain();
    osc.connect(gain);
    gain.connect(ctx.destination);

    const now = ctx.currentTime;
    if (type === 'success') {
      osc.type = 'triangle';
      osc.frequency.setValueAtTime(261.63, now); 
      osc.frequency.setValueAtTime(329.63, now + 0.08); 
      osc.frequency.setValueAtTime(392.00, now + 0.16); 
      osc.frequency.setValueAtTime(523.25, now + 0.24); 
      gain.gain.setValueAtTime(0.15, now);
      gain.gain.exponentialRampToValueAtTime(0.01, now + 0.4);
      osc.start(now);
      osc.stop(now + 0.4);
    } else if (type === 'click') {
      osc.type = 'sine';
      osc.frequency.setValueAtTime(587.33, now); 
      osc.frequency.exponentialRampToValueAtTime(200, now + 0.08);
      gain.gain.setValueAtTime(0.1, now);
      gain.gain.exponentialRampToValueAtTime(0.01, now + 0.08);
      osc.start(now);
      osc.stop(now + 0.08);
    } else if (type === 'complete') {
      osc.type = 'sawtooth';
      osc.frequency.setValueAtTime(392.00, now);
      osc.frequency.setValueAtTime(523.25, now + 0.05);
      osc.frequency.setValueAtTime(659.25, now + 0.1);
      osc.frequency.setValueAtTime(783.99, now + 0.15);
      gain.gain.setValueAtTime(0.12, now);
      gain.gain.exponentialRampToValueAtTime(0.01, now + 0.6);
      osc.start(now);
      osc.stop(now + 0.6);
    } else if (type === 'error') {
      osc.type = 'sawtooth';
      osc.frequency.setValueAtTime(180, now);
      osc.frequency.setValueAtTime(130, now + 0.12);
      gain.gain.setValueAtTime(0.12, now);
      gain.gain.exponentialRampToValueAtTime(0.01, now + 0.25);
      osc.start(now);
      osc.stop(now + 0.25);
    }
  } catch (e) {
    console.warn('AudioContext failed to trigger.', e);
  }
};

const INITIAL_SAGA_DATA = [
  {
    id: 'subject-1',
    name: 'Môn: Tiếng Nhật N3 🇯🇵',
    month: 'Mục tiêu: Đậu N3 đợt Tháng 7',
    emoji: '🏆',
    regions: [
      {
        id: 'skill-1-1',
        name: 'Kỹ năng: Từ Vựng & Hán Tự ✍️',
        description: 'Luyện 50 từ vựng Kanji mỗi ngày',
        color: 'from-blue-500 to-indigo-600',
        level: 1,
        xp: 320,
        streak: 3,
        goals: {
          longTerm: 'Đạt JLPT N3 phục vụ công việc tại Tokyo 🇯🇵',
          shortTerm: 'Nhớ hết 500 từ vựng Kanji căn bản trong 2 tuần',
          reason: 'Dễ dàng đọc tài liệu kỹ thuật Nhật Bản và tăng thu nhập',
          deadline: '30/07/2026',
          dreamVersion: 'Giao tiếp trôi chảy và tự tin với đồng nghiệp người Nhật Bản!'
        },
        roadmap: [
          { id: 'm1', text: 'Hoàn thành bảng chữ cái bổ sung Kanji cấp tiểu học', completed: true },
          { id: 'm2', text: 'Học 150 danh từ Kanji thông dụng chỉ đồ vật', completed: true },
          { id: 'm3', text: 'Nhận biết 100 động từ ghép phức tạp', completed: false },
          { id: 'm4', text: 'Làm trọn vẹn 3 đề thi thử Hán tự năm 2025', completed: false }
        ],
        levels: [
          { 
            id: 'lvl-1-1-1', 
            num: 1, 
            name: 'Ngày 1: Hán tự Kanji Cơ Bản', 
            x: 12, 
            y: 75, 
            tasks: [
              { id: 't1', text: 'Học 10 chữ Kanji thuộc bộ Nhân', completed: true }, 
              { id: 't2', text: 'Làm bài tập điền từ Minna no Nihongo', completed: true }
            ],
            links: [{ name: 'Bảng tra cứu Kanji', url: 'https://mazii.net' }],
            files: []
          },
          { 
            id: 'lvl-1-1-2', 
            num: 2, 
            name: 'Ngày 2: Kanji chỉ Hành Động', 
            x: 32, 
            y: 35, 
            tasks: [{ id: 't3', text: 'Xem video giải thích ngữ pháp Shinkanzen', completed: false }],
            links: [],
            files: []
          },
          { id: 'lvl-1-1-3', num: 3, name: 'Ngày 3: Ôn tập Kanji Tuần 1', x: 52, y: 68, tasks: [], links: [], files: [] },
          { id: 'lvl-1-1-4', num: 4, name: 'Ngày 4: Nhận diện mặt chữ nhanh', x: 72, y: 30, tasks: [], links: [], files: [] },
          { id: 'lvl-1-1-5', num: 5, name: 'Ngày 5: Bài kiểm tra Kanji tổng hợp', x: 90, y: 65, tasks: [], links: [], files: [] }
        ]
      },
      {
        id: 'skill-1-2',
        name: 'Kỹ năng: Luyện Nghe Hiểu (Choukai) 🎧',
        description: 'Luyện phản xạ nghe đề thi thực tế',
        color: 'from-orange-500 to-amber-600',
        level: 1,
        xp: 150,
        streak: 1,
        goals: {
          longTerm: 'Nghe hiểu tin tức thời sự NHK mà không cần phụ đề',
          shortTerm: 'Luyện 15 phút Choukai nghe tranh mỗi sáng',
          reason: 'Bù đắp điểm số yếu nhất trong các kỹ năng',
          deadline: '20/07/2026',
          dreamVersion: 'Xem phim hoạt hình Anime Nhật hiểu trực tiếp!'
        },
        roadmap: [
          { id: 'm1-2-1', text: 'Tập trung nghe phân biệt âm đục, âm ngắt', completed: true },
          { id: 'm1-2-2', text: 'Làm quen dạng bài hội thoại ngắn xin lỗi/cảm ơn', completed: false }
        ],
        levels: [
          { id: 'lvl-1-2-1', num: 1, name: 'Ngày 1: Nghe hội thoại ngắn JLPT', x: 12, y: 75, tasks: [], links: [], files: [] },
          { id: 'lvl-1-2-2', num: 2, name: 'Ngày 2: Phân biệt âm đục & ngắt', x: 32, y: 35, tasks: [], links: [], files: [] },
          { id: 'lvl-1-2-3', num: 3, name: 'Ngày 3: Luyện nghe tranh vẽ', x: 52, y: 68, tasks: [], links: [], files: [] },
          { id: 'lvl-1-2-4', num: 4, name: 'Ngày 4: Nghe tin tức NHK Easy', x: 72, y: 30, tasks: [], links: [], files: [] },
          { id: 'lvl-1-2-5', num: 5, name: 'Ngày 5: Điền từ chính tả bài nghe', x: 90, y: 65, tasks: [], links: [], files: [] }
        ]
      }
    ]
  }
];

const INITIAL_NOTES_BY_REGION = {
  'skill-1-1': [
    { id: 'n-1', title: 'Mẹo nhớ chữ Kanji Nhân (人) ✍️', content: 'Kanji chữ Nhân trông giống như một người đang đứng giang rộng hai chân làm điểm tựa vững vàng. Ghép với chữ khác thường mang ý nghĩa liên quan đến hoạt động của con người!', date: '28/05/2026', color: 'bg-yellow-100' }
  ]
};

const INITIAL_FLASHCARDS_BY_REGION = {
  'skill-1-1': [
    {
      id: 1,
      q: "Hán tự 'Nhân' (人) âm ôn đọc là gì?",
      a: "Jin hoặc Nin",
      options: ["Jin hoặc Nin", "Kou", "Shin", "Matsu"],
      flipped: false
    }
  ]
};

const INITIAL_MATCHING_TERMS_BY_REGION = {
  'skill-1-1': [
    { id: 't-1', text: '人 (Nhân)', matchId: 'pair-1' },
    { id: 't-2', text: '水 (Thủy)', matchId: 'pair-2' },
  ]
};

const INITIAL_MATCHING_DEFS_BY_REGION = {
  'skill-1-1': [
    { id: 'd-1', text: 'Con người / Nhân loại', matchId: 'pair-1' },
    { id: 'd-2', text: 'Nước / Chất lỏng sinh hoạt', matchId: 'pair-2' },
  ]
};

const INITIAL_DIARY_ENTRIES = [
  {
    id: 101,
    date: '28/05/2026',
    mood: '🌟 Rất Tốt',
    text: 'Hôm nay mình đã hoàn thành 2 chu kỳ Pomodoro học Kanji cực xuất sắc và tập 15 phút Cardio theo link đính kèm! Cố gắng duy trì nhé! 🐾🚀',
    image: 'https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?auto=format&fit=crop&q=80&w=400'
  }
];

const INITIAL_WORKOUT_ROUTINES = [
  { id: 'w-1', name: 'Nhảy dây tốc độ cao ⏱️', sets: '5 hiệp', reps: '100 cái/hiệp', link: 'https://www.youtube.com/watch?v=u31qwQUeGuM', completed: false },
  { id: 'w-2', name: 'Squat & Plank rèn sức bền 🏋️‍♂️', sets: '3 hiệp', reps: '15 Squat + 1p Plank', link: '', completed: false }
];

export default function App() {
  // Trạng thái Cloud/Database
  const [dbConfigInput, setDbConfigInput] = useState('');
  const [activeFirebaseConfig, setActiveFirebaseConfig] = useState(null);
  const [firestoreDb, setFirestoreDb] = useState(null);
  const [isCloudLoading, setIsCloudLoading] = useState(false);
  const [cloudError, setCloudError] = useState('');
  const [syncStatus, setSyncStatus] = useState('Offline Mode (Dữ liệu cục bộ)');

  // Trạng thái Phòng/Workspace
  const [roomPasscode, setRoomPasscode] = useState('');
  const [workspaceNameInput, setWorkspaceNameInput] = useState('');
  const [activeRoom, setActiveRoom] = useState(null); 

  // Trạng thái giao diện & Âm thanh
  const [activeTab, setActiveTab] = useState('map'); 
  const [isMuted, setIsMuted] = useState(false);
  const [dopamineAlert, setDopamineAlert] = useState(null);
  const [levelUpAlert, setLevelUpAlert] = useState(null);

  // Slogan tự viết (Tương tự ảnh mẫu image_cb01ee.png và image_cb020e.png)
  const [headerQuote, setHeaderQuote] = useState('Mỗi bước đi nhỏ trên bản đồ đều đưa bạn đến gần đích hơn đó! 🐾');
  const [footerQuote, setFooterQuote] = useState('Dù hôm nay bạn chỉ hoàn thành 1 đầu việc nhỏ hay chỉ uống đủ nước, Snoopy vẫn luôn reo hò hạnh phúc vì những cố gắng phi thường của bạn!');

  // Bản đồ Saga Candy Crush (Cập nhật theo môn học, kỹ năng, ngày học)
  const [sagaData, setSagaData] = useState(INITIAL_SAGA_DATA);
  const [activeCountryId, setActiveCountryId] = useState('subject-1'); // Subject
  const [activeRegionId, setActiveRegionId] = useState('skill-1-1'); // Skill/Unit
  const [activeLevelId, setActiveLevelId] = useState('lvl-1-1-1'); // Day/Level
  const [unlockedLevelNum, setUnlockedLevelNum] = useState(2); 

  const [newCountryName, setNewCountryName] = useState('');
  const [newCountryMonth, setNewCountryMonth] = useState('');
  const [newRegionName, setNewRegionName] = useState('');
  const [newRegionDesc, setNewRegionDesc] = useState('');

  // Todo-list hàng ngày
  const [newTaskText, setNewTaskText] = useState('');
  const [timeLeft, setTimeLeft] = useState(25 * 60);
  const [isActive, setIsActive] = useState(false);
  const [timerMode, setTimerMode] = useState('focus'); 

  // Thêm tài liệu học tập (Links & Files) cho Ngày học hiện tại
  const [newLinkName, setNewLinkName] = useState('');
  const [newLinkUrl, setNewLinkUrl] = useState('');
  const fileInputRefDay = useRef(null);

  // Biểu đồ Focus hàng tuần (T2 - CN)
  const [weeklyData, setWeeklyData] = useState([
    { day: 'T2', val: 50, label: '50p' },
    { day: 'T3', val: 110, label: '110p' },
    { day: 'T4', val: 30, label: '30p' },
    { day: 'T5', val: 75, label: '75p' },
    { day: 'T6', val: 0, label: '0p' },
    { day: 'T7', val: 125, label: '125p' },
    { day: 'CN', val: 40, label: '40p' },
  ]);

  // Sức khỏe BMI, Lượng nước, & Thể dục
  const [height, setHeight] = useState('165');
  const [weight, setWeight] = useState('60');
  const [targetWeight, setTargetWeight] = useState('55');
  const [bmi, setBmi] = useState(null);
  const [dietSuggestion, setDietSuggestion] = useState('');
  const [waterGlasses, setWaterGlasses] = useState(3); 
  const [targetWaterGlasses, setTargetWaterGlasses] = useState(8);
  const [targetWaterLiters, setTargetWaterLiters] = useState(2.3);
  const [isAiDietLoading, setIsAiDietLoading] = useState(false);

  // Giáo án tập thể dục (Workout Tracker)
  const [workoutRoutines, setWorkoutRoutines] = useState(INITIAL_WORKOUT_ROUTINES);
  const [newWorkoutName, setNewWorkoutName] = useState('');
  const [newWorkoutSets, setNewWorkoutSets] = useState('');
  const [newWorkoutReps, setNewWorkoutReps] = useState('');
  const [newWorkoutLink, setNewWorkoutLink] = useState('');

  // Màn hình khóa Zen Screen
  const [lockscreenNotes, setLockscreenNotes] = useState([
    { id: 1, text: 'Học Kanji từ vựng trước 10h sáng ⏰', pinned: true },
    { id: 2, text: 'Uống thêm nước ấm nha 💧', pinned: true }
  ]);
  const [newLockNote, setNewLockNote] = useState('');
  const [lockTime, setLockTime] = useState('');
  const [lockscreenSlogan, setLockscreenSlogan] = useState('Hãy thở đều và tập trung làm việc nhé! 🌸');

  // Ghi chú và Đấu trường ôn tập theo TỪNG VÙNG ĐẤT (HỌC PHẦN)
  const [notesByRegion, setNotesByRegion] = useState(INITIAL_NOTES_BY_REGION);
  const [flashcardsByRegion, setFlashcardsByRegion] = useState(INITIAL_FLASHCARDS_BY_REGION);
  const [matchingTermsByRegion, setMatchingTermsByRegion] = useState(INITIAL_MATCHING_TERMS_BY_REGION);
  const [matchingDefsByRegion, setMatchingDefsByRegion] = useState(INITIAL_MATCHING_DEFS_BY_REGION);

  // Thêm ghi chú mới
  const [newNoteTitle, setNewNoteTitle] = useState('');
  const [newNoteContent, setNewNoteContent] = useState('');
  const [newNoteColor, setNewNoteColor] = useState('bg-yellow-100');

  // Trạng thái đấu trường ôn tập
  const [reviewMode, setReviewMode] = useState('match'); 
  const [typeInputs, setTypeInputs] = useState({});
  
  // Tạo Thẻ Lật mới
  const [newCardQ, setNewCardQ] = useState('');
  const [newCardA, setNewCardA] = useState('');
  const [newCardOpt2, setNewCardOpt2] = useState('');
  const [newCardOpt3, setNewCardOpt3] = useState('');
  const [newCardOpt4, setNewCardOpt4] = useState('');

  // Nối cặp (Matching)
  const [selectedTerm, setSelectedTerm] = useState(null);
  const [selectedDef, setSelectedDef] = useState(null);
  const [matchedPairs, setMatchedPairs] = useState([]);
  const [matchGameStatus, setMatchGameStatus] = useState('Hãy chọn một thuật ngữ ở cột trái rồi tìm định nghĩa đúng ở cột phải nhé! 🐾');

  const [newTermText, setNewTermText] = useState('');
  const [newDefText, setNewDefText] = useState('');

  // Nhật ký động lực
  const [journalEntries, setJournalEntries] = useState(INITIAL_DIARY_ENTRIES);
  const [newJournalText, setNewJournalText] = useState('');
  const [newJournalMood, setNewJournalMood] = useState('🌟 Rất Tốt');
  const [journalImagePreview, setJournalImagePreview] = useState(null);
  const fileInputRef = useRef(null);

  // Smart Study Planner State
  const [plannerFreeHours, setPlannerFreeHours] = useState('4 tiếng buổi chiều');
  const [plannerDeadline, setPlannerDeadline] = useState('3 tuần tới thi');
  const [plannerPriority, setPlannerPriority] = useState('Cao ⚡');
  const [plannerSuggestedSchedule, setPlannerSuggestedSchedule] = useState([
    { time: '08:00 - 09:30', activity: 'Học lý thuyết mới (Tập trung cao)', break: '15p' },
    { time: '10:00 - 11:30', activity: 'Làm bài tập vận dụng & Flashcards', break: '20p' },
    { time: '14:00 - 15:30', activity: 'Luyện đề thi thử hoặc nghe Choukai', break: '15p' }
  ]);
  const [isPlannerLoading, setIsPlannerLoading] = useState(false);

  // Gemini AI Integration
  const [aiApiKey, setAiApiKey] = useState(''); 
  const [aiPrompt, setAiPrompt] = useState('');
  const [aiChatHistory, setAiChatHistory] = useState([
    { role: 'model', text: 'Gâu gâu! Trợ lý ảo Snoopy thông thái hỗ trợ học tập đã trực sẵn. Bạn cần tôi thiết lập thời khóa biểu hay phân tích tài liệu học nào không?' }
  ]);
  const [isAiLoading, setIsAiLoading] = useState(false);
  const [confettiActive, setConfettiActive] = useState(false);

  // State hỗ trợ tạo mới cột mốc cho Roadmap
  const [newMilestoneText, setNewMilestoneText] = useState('');

  useEffect(() => {
    const savedCustomConfig = localStorage.getItem('snoopy_custom_firebase_config');
    if (savedCustomConfig) {
      try {
        const parsed = JSON.parse(savedCustomConfig);
        setActiveFirebaseConfig(parsed);
        setDbConfigInput(JSON.stringify(parsed, null, 2));
        initFirebase(parsed);
      } catch (err) {
        console.warn("Invalid stored firebase configuration. Using sandbox config.", err);
        initFirebase(DEFAULT_FIREBASE_CONFIG);
      }
    } else {
      initFirebase(DEFAULT_FIREBASE_CONFIG);
    }
  }, []);

  const initFirebase = (config) => {
    try {
      if (config.apiKey && config.apiKey.includes("sandbox-config-key")) {
        setFirestoreDb(null);
        setSyncStatus('🟢 Chế độ Offline Local (Dữ liệu an toàn trên thiết bị)');
        return;
      }
      
      const app = initializeApp(config);
      const db = getFirestore(app);
      setFirestoreDb(db);
      setSyncStatus('🟢 Kết nối máy chủ Cloud thành công!');
    } catch (err) {
      console.error("Firebase init failed, switching to Offline Local mode gracefully:", err);
      setFirestoreDb(null);
      setSyncStatus('🔴 Lỗi kết nối Cloud. Đang chạy ở chế độ Offline Local.');
    }
  };

  const handleSaveCustomConfig = (e) => {
    e.preventDefault();
    try {
      const parsed = JSON.parse(dbConfigInput);
      localStorage.setItem('snoopy_custom_firebase_config', JSON.stringify(parsed));
      setActiveFirebaseConfig(parsed);
      initFirebase(parsed);
      triggerDopamine("💾 Cập nhật máy chủ cá nhân thành công!", 3);
    } catch (err) {
      setCloudError("Cú pháp JSON cấu hình không hợp lệ. Hãy kiểm tra lại dấu ngoặc và dấu phẩy.");
      playAudioFeedback('error', isMuted);
    }
  };

  const handleResetConfigToDefault = () => {
    localStorage.removeItem('snoopy_custom_firebase_config');
    setActiveFirebaseConfig(null);
    setDbConfigInput('');
    initFirebase(DEFAULT_FIREBASE_CONFIG);
    triggerDopamine("🔄 Khôi phục máy chủ dùng chung thành công!", 3);
  };

  const calculateBMIAndWater = () => {
    if (!weight || !height) return;
    const heightInMeters = parseFloat(height) / 100;
    const calculatedBmi = (parseFloat(weight) / (heightInMeters * heightInMeters)).toFixed(1);
    setBmi(calculatedBmi);

    // Tính lượng nước dựa vào BMI & Mục tiêu giảm cân
    let waterLiters = (parseFloat(weight) * 0.033);
    const target = parseFloat(targetWeight) || parseFloat(weight);
    const isLosingWeight = target < parseFloat(weight);

    // Tăng thêm 0.5L nước nếu có mục tiêu giảm cân giúp tăng tốc độ đào thải
    if (isLosingWeight) {
      waterLiters += 0.5;
    }

    setTargetWaterLiters(parseFloat(waterLiters.toFixed(2)));
    const totalGlasses = Math.ceil(waterLiters / 0.25);
    setTargetWaterGlasses(totalGlasses);

    let tip = '';
    if (calculatedBmi < 18.5) {
      tip = `BMI của bạn là ${calculatedBmi} (Nhẹ cân). Mục tiêu uống ${waterLiters.toFixed(1)}L nước hàng ngày. Bạn nhớ bổ sung thêm chất béo lành mạnh và protein nhé! 🍳🌱`;
    } else if (calculatedBmi >= 18.5 && calculatedBmi <= 24.9) {
      tip = `BMI của bạn là ${calculatedBmi} (Bình thường). Cơ thể bạn đang cực kỳ cân đối. Hãy duy trì đủ ${waterLiters.toFixed(1)}L nước để bảo vệ năng lượng cho não bộ học tập! 🧠💦`;
    } else {
      tip = `BMI của bạn là ${calculatedBmi} (Thừa cân nhẹ). Uống đủ ${waterLiters.toFixed(1)}L nước hàng ngày sẽ giúp hỗ trợ đào thải năng lượng dư thừa cực tốt và giảm cảm giác thèm ăn vặt khi học! 🏃‍♂️🥗`;
    }
    setDietSuggestion(tip);
  };

  useEffect(() => {
    calculateBMIAndWater();
  }, [weight, height, targetWeight]);

  useEffect(() => {
    if (!activeRoom) return;

    const delayDebounceFn = setTimeout(async () => {
      setSyncStatus('⚡ Đang tự động lưu...');
      const payloadState = {
        sagaData,
        waterGlasses,
        weeklyData,
        journalEntries,
        lockscreenNotes,
        aiApiKey,
        headerQuote,
        footerQuote,
        unlockedLevelNum,
        height,
        weight,
        targetWeight,
        lockscreenSlogan,
        notesByRegion,
        flashcardsByRegion,
        matchingTermsByRegion,
        matchingDefsByRegion,
        workoutRoutines,
        plannerSuggestedSchedule
      };

      // Lưu trữ ngoại tuyến
      localStorage.setItem(`offline_room_${activeRoom}`, JSON.stringify(payloadState));

      // Thử đồng bộ Cloud
      if (firestoreDb) {
        try {
          const docRef = doc(firestoreDb, "workspaces", activeRoom);
          await setDoc(docRef, {
            lastSavedAt: new Date().toISOString(),
            appState: payloadState
          }, { merge: true });
          setSyncStatus('🟢 Đã đồng bộ Cloud hoàn tất!');
        } catch (err) {
          console.warn("Cloud Sync failed. Saved locally instead:", err);
          setSyncStatus('⚠️ Lưu ngoại tuyến (Đang offline)');
        }
      } else {
        setSyncStatus('🟢 Đã lưu vào trình duyệt của bạn!');
      }
    }, 1500); 

    return () => clearTimeout(delayDebounceFn);
  }, [
    sagaData, waterGlasses, weeklyData, journalEntries, lockscreenNotes, 
    aiApiKey, headerQuote, footerQuote, unlockedLevelNum, height, weight, 
    targetWeight, lockscreenSlogan, notesByRegion, flashcardsByRegion, 
    matchingTermsByRegion, matchingDefsByRegion, activeRoom, firestoreDb, workoutRoutines,
    plannerSuggestedSchedule
  ]);

  useEffect(() => {
    const savedSessionRoom = sessionStorage.getItem('snoopy_active_session_room');
    if (savedSessionRoom) {
      setActiveRoom(savedSessionRoom);
      triggerDopamine(`🔓 Chào mừng bạn quay trở lại phòng: ${savedSessionRoom}!`, 3);
    }
  }, []);

  useEffect(() => {
    let interval = null;
    if (isActive && timeLeft > 0) {
      interval = setInterval(() => {
        setTimeLeft((time) => time - 1);
      }, 1000);
    } else if (timeLeft === 0 && isActive) {
      setIsActive(false);
      if (timerMode === 'focus') {
        setTimerMode('break');
        setTimeLeft(5 * 60);
        triggerDopamine("Hoàn thành chu kỳ! Snoopy thưởng bạn 5 phút xả hơi! 🐾🏆", 8, true);
        gainXP(50);
        updateWeeklyFocus(25);
      } else {
        setTimerMode('focus');
        setTimeLeft(25 * 60);
        triggerDopamine("Quay lại đường đua cùng chú cún Snoopy thôi nào! ⚡🐾", 5);
      }
    }
    return () => clearInterval(interval);
  }, [isActive, timeLeft, timerMode]);

  const updateWeeklyFocus = (minutes) => {
    const days = ['CN', 'T2', 'T3', 'T4', 'T5', 'T6', 'T7'];
    const currentDayName = days[new Date().getDay()];
    setWeeklyData(prev => prev.map(item => {
      if (item.day === currentDayName) {
        const newVal = item.val + minutes;
        return { ...item, val: newVal, label: `${newVal}p` };
      }
      return item;
    }));
  };

  const toggleTimer = () => {
    setIsActive(!isActive);
  };

  const resetTimer = () => {
    setIsActive(false);
    setTimeLeft(timerMode === 'focus' ? 25 * 60 : 5 * 60);
  };

  useEffect(() => {
    const updateTime = () => {
      const now = new Date();
      let hours = now.getHours().toString().padStart(2, '0');
      let minutes = now.getMinutes().toString().padStart(2, '0');
      let seconds = now.getSeconds().toString().padStart(2, '0');
      setLockTime(`${hours}:${minutes}:${seconds}`);
    };
    updateTime();
    const interval = setInterval(updateTime, 1000);
    return () => clearInterval(interval);
  }, []);

  // Hàm xử lý tăng XP và thăng cấp (RPG Level System)
  const gainXP = (amount) => {
    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          if (region.id === activeRegionId) {
            let nextXp = (region.xp || 0) + amount;
            let currentLevel = region.level || 1;
            const xpNeeded = 1000;

            if (nextXp >= xpNeeded) {
              currentLevel += 1;
              nextXp -= xpNeeded;
              playAudioFeedback('complete', isMuted);
              setLevelUpAlert({
                skillName: region.name,
                level: currentLevel
              });
              setTimeout(() => {
                setLevelUpAlert(null);
              }, 6000);
            }
            return {
              ...region,
              level: currentLevel,
              xp: nextXp
            };
          }
          return region;
        })
      };
    });
    setSagaData(updatedSaga);
  };

  const triggerDopamine = (message, starsCount = 3, isCompleteLevel = false) => {
    playAudioFeedback(isCompleteLevel ? 'complete' : 'success', isMuted);
    setDopamineAlert({
      id: Date.now(),
      message,
      stars: Array.from({ length: starsCount })
    });
    setConfettiActive(true);
    setTimeout(() => {
      setDopamineAlert(null);
      setConfettiActive(false);
    }, 4500);
  };

  const applyWorkspaceState = (state) => {
    if (state.sagaData) setSagaData(state.sagaData);
    if (state.waterGlasses !== undefined) setWaterGlasses(state.waterGlasses);
    if (state.weeklyData) setWeeklyData(state.weeklyData);
    if (state.journalEntries) setJournalEntries(state.journalEntries);
    if (state.lockscreenNotes) setLockscreenNotes(state.lockscreenNotes);
    if (state.aiApiKey !== undefined) setAiApiKey(state.aiApiKey);
    if (state.headerQuote) setHeaderQuote(state.headerQuote);
    if (state.footerQuote) setFooterQuote(state.footerQuote);
    if (state.unlockedLevelNum) setUnlockedLevelNum(state.unlockedLevelNum);
    if (state.height) setHeight(state.height);
    if (state.weight) setWeight(state.weight);
    if (state.targetWeight) setTargetWeight(state.targetWeight);
    if (state.lockscreenSlogan) setLockscreenSlogan(state.lockscreenSlogan);
    if (state.notesByRegion) setNotesByRegion(state.notesByRegion);
    if (state.flashcardsByRegion) setFlashcardsByRegion(state.flashcardsByRegion);
    if (state.matchingTermsByRegion) setMatchingTermsByRegion(state.matchingTermsByRegion);
    if (state.matchingDefsByRegion) setMatchingDefsByRegion(state.matchingDefsByRegion);
    if (state.workoutRoutines) setWorkoutRoutines(state.workoutRoutines);
    if (state.plannerSuggestedSchedule) setPlannerSuggestedSchedule(state.plannerSuggestedSchedule);
  };

  const handleRegisterWorkspace = async (e) => {
    e.preventDefault();
    const wName = workspaceNameInput.trim().toLowerCase();
    const pass = roomPasscode.trim();

    if (!wName || !pass) {
      setCloudError("Vui lòng nhập tên phòng và mật khẩu đầy đủ!");
      return;
    }

    setIsCloudLoading(true);
    setCloudError('');
    playAudioFeedback('click', isMuted);

    const clientHashed = await hashPasscode(pass);
    const defaultState = {
      sagaData: INITIAL_SAGA_DATA,
      waterGlasses: 3,
      weeklyData: [
        { day: 'T2', val: 0, label: '0p' },
        { day: 'T3', val: 0, label: '0p' },
        { day: 'T4', val: 0, label: '0p' },
        { day: 'T5', val: 0, label: '0p' },
        { day: 'T6', val: 0, label: '0p' },
        { day: 'T7', val: 0, label: '0p' },
        { day: 'CN', val: 0, label: '0p' }
      ],
      journalEntries: INITIAL_DIARY_ENTRIES,
      lockscreenNotes: [
        { id: 1, text: 'Chúc bạn một ngày mới đầy năng lượng tập trung nhé! 🌟', pinned: true }
      ],
      aiApiKey: '',
      headerQuote: 'Mỗi bước đi nhỏ trên bản đồ đều đưa bạn đến gần đích hơn đó! 🐾',
      footerQuote: 'Dù hôm nay bạn chỉ hoàn thành 1 đầu việc nhỏ hay chỉ uống đủ nước, Snoopy vẫn luôn reo hò hạnh phúc vì những cố gắng phi thường của bạn!',
      unlockedLevelNum: 1,
      height: '165',
      weight: '60',
      targetWeight: '55',
      lockscreenSlogan: 'Hãy thở đều và tập trung làm việc nhé! 🌸',
      notesByRegion: INITIAL_NOTES_BY_REGION,
      flashcardsByRegion: INITIAL_FLASHCARDS_BY_REGION,
      matchingTermsByRegion: INITIAL_MATCHING_TERMS_BY_REGION,
      matchingDefsByRegion: INITIAL_MATCHING_DEFS_BY_REGION,
      workoutRoutines: INITIAL_WORKOUT_ROUTINES,
      plannerSuggestedSchedule: [
        { time: '08:00 - 09:30', activity: 'Tập trung học lý thuyết (XP cao)', break: '15p' },
        { time: '10:00 - 11:30', activity: 'Làm Flashcard ôn tập', break: '20p' }
      ]
    };

    let registeredOnCloud = false;

    if (firestoreDb) {
      try {
        const docRef = doc(firestoreDb, "workspaces", wName);
        const docSnap = await getDoc(docRef);

        if (docSnap.exists()) {
          setCloudError(`Tên phòng "${wName}" đã được đăng ký. Vui lòng đăng nhập hoặc chọn tên khác!`);
          setIsCloudLoading(false);
          playAudioFeedback('error', isMuted);
          return;
        }

        const initialPayload = {
          hashedPasscode: clientHashed,
          createdAt: new Date().toISOString(),
          lastSavedAt: new Date().toISOString(),
          appState: defaultState
        };

        await setDoc(docRef, initialPayload);
        registeredOnCloud = true;
      } catch (err) {
        console.warn("Cloud connection error, saving offline locally:", err);
      }
    }

    try {
      localStorage.setItem(`offline_room_${wName}`, JSON.stringify(defaultState));
      localStorage.setItem(`offline_passcode_${wName}`, clientHashed);

      setActiveRoom(wName);
      sessionStorage.setItem('snoopy_active_session_room', wName);
      applyWorkspaceState(defaultState);

      if (registeredOnCloud) {
        triggerDopamine(`🎉 Phòng riêng "${wName}" đã được tạo thành công trên Cloud!`, 5);
      } else {
        triggerDopamine(`⚠️ Máy chủ ngoại tuyến! Đã tạo phòng "${wName}" ở chế độ Offline Local!`, 5);
      }
    } catch (err) {
      console.error(err);
      setCloudError("Không thể khởi tạo bộ nhớ cục bộ.");
    } finally {
      setIsCloudLoading(false);
    }
  };

  const handleLoginWorkspace = async (e) => {
    e.preventDefault();
    const wName = workspaceNameInput.trim().toLowerCase();
    const pass = roomPasscode.trim();

    if (!wName || !pass) {
      setCloudError("Vui lòng nhập tên phòng và mật khẩu đầy đủ!");
      return;
    }

    setIsCloudLoading(true);
    setCloudError('');
    playAudioFeedback('click', isMuted);

    const clientHashed = await hashPasscode(pass);

    if (firestoreDb) {
      try {
        const docRef = doc(firestoreDb, "workspaces", wName);
        const docSnap = await getDoc(docRef);

        if (docSnap.exists()) {
          const dbData = docSnap.data();
          if (dbData.hashedPasscode === clientHashed) {
            setActiveRoom(wName);
            sessionStorage.setItem('snoopy_active_session_room', wName);
            if (dbData.appState) applyWorkspaceState(dbData.appState);
            
            triggerDopamine(`🔓 Đăng nhập phòng "${wName}" thành công từ Cloud!`, 4);
            setIsCloudLoading(false);
            return;
          } else {
            setCloudError("Mật mã không đúng. Vui lòng kiểm tra lại phòng học cá nhân của bạn.");
            setIsCloudLoading(false);
            playAudioFeedback('error', isMuted);
            return;
          }
        }
      } catch (err) {
        console.warn("Firestore fetch failed, switching to LocalStorage fallback:", err);
      }
    }

    const offlineData = localStorage.getItem(`offline_room_${wName}`);
    if (offlineData) {
      try {
        const parsed = JSON.parse(offlineData);
        const localHashed = localStorage.getItem(`offline_passcode_${wName}`);
        
        if (localHashed && localHashed !== clientHashed) {
          setCloudError("Mật mã offline cho phòng này không chính xác.");
          setIsCloudLoading(false);
          playAudioFeedback('error', isMuted);
          return;
        }

        setActiveRoom(wName);
        sessionStorage.setItem('snoopy_active_session_room', wName);
        applyWorkspaceState(parsed);

        triggerDopamine(`⚠️ Offline Mode! Đã mở phòng "${wName}" từ thiết bị thành công!`, 3);
        setIsCloudLoading(false);
        return;
      } catch (e) {
        console.error("Failed to parse fallback offline state:", e);
      }
    }

    setCloudError(`Không tìm thấy dữ liệu cho phòng "${wName}".`);
    setIsCloudLoading(false);
    playAudioFeedback('error', isMuted);
  };

  const handleLockRoom = () => {
    setActiveRoom(null);
    sessionStorage.removeItem('snoopy_active_session_room');
    setRoomPasscode('');
    setWorkspaceNameInput('');
    playAudioFeedback('error', isMuted);
  };

  // Quản lý Todo-list theo từng Ngày học
  const handleToggleMapTask = (taskId) => {
    let isAllDone = false;
    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          return {
            ...region,
            levels: region.levels.map(level => {
              if (level.id === activeLevelId) {
                const updatedTasks = level.tasks.map(t => {
                  if (t.id === taskId) {
                    const nextVal = !t.completed;
                    if (nextVal) {
                      playAudioFeedback('click', isMuted);
                      gainXP(10); // Mỗi task hoàn thành được +10 XP
                    }
                    return { ...t, completed: nextVal };
                  }
                  return t;
                });
                
                const done = updatedTasks.length > 0 && updatedTasks.every(t => t.completed);
                if (done) isAllDone = true;
                return { ...level, tasks: updatedTasks };
              }
              return level;
            })
          };
        })
      };
    });

    setSagaData(updatedSaga);
    if (isAllDone) {
      setUnlockedLevelNum(prev => prev + 1);
      gainXP(100); // Thăng cấp ngày học được +100 XP
      triggerDopamine("Chúc mừng! Bạn đã hoàn thành mọi ải trong ngày để giải cứu Snoopy! 🐶🏆", 3, true);
    }
  };

  const handleAddMapTask = (e) => {
    e.preventDefault();
    if (!newTaskText.trim()) return;

    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          return {
            ...region,
            levels: region.levels.map(level => {
              if (level.id === activeLevelId) {
                return {
                  ...level,
                  tasks: [...(level.tasks || []), { id: `task-${Date.now()}`, text: newTaskText, completed: false }]
                };
              }
              return level;
            })
          };
        })
      };
    });

    setSagaData(updatedSaga);
    setNewTaskText('');
    playAudioFeedback('click', isMuted);
  };

  const handleDeleteMapTask = (taskId) => {
    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          return {
            ...region,
            levels: region.levels.map(level => {
              if (level.id === activeLevelId) {
                return {
                  ...level,
                  tasks: (level.tasks || []).filter(t => t.id !== taskId)
                };
              }
              return level;
            })
          };
        })
      };
    });
    setSagaData(updatedSaga);
    playAudioFeedback('error', isMuted);
  };

  // Thêm Tài liệu (Link & File) vào Ngày học
  const handleAddStudyLink = (e) => {
    e.preventDefault();
    if (!newLinkName.trim() || !newLinkUrl.trim()) return;

    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          return {
            ...region,
            levels: region.levels.map(level => {
              if (level.id === activeLevelId) {
                return {
                  ...level,
                  links: [...(level.links || []), { name: newLinkName, url: newLinkUrl.trim() }]
                };
              }
              return level;
            })
          };
        })
      };
    });

    setSagaData(updatedSaga);
    setNewLinkName('');
    setNewLinkUrl('');
    triggerDopamine("🔗 Gắn tài liệu liên kết thành công!", 2);
  };

  const handleDeleteStudyLink = (linkIdx) => {
    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          return {
            ...region,
            levels: region.levels.map(level => {
              if (level.id === activeLevelId) {
                return {
                  ...level,
                  links: (level.links || []).filter((_, idx) => idx !== linkIdx)
                };
              }
              return level;
            })
          };
        })
      };
    });
    setSagaData(updatedSaga);
    playAudioFeedback('error', isMuted);
  };

  const handleStudyFileUpload = (e) => {
    const file = e.target.files[0];
    if (!file) return;

    // Đọc metadata của file để dán vào Ngày học
    const newFileMeta = {
      name: file.name,
      size: (file.size / 1024).toFixed(1) + ' KB',
      type: file.type,
      uploadedAt: new Date().toLocaleDateString('vi-VN')
    };

    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          return {
            ...region,
            levels: region.levels.map(level => {
              if (level.id === activeLevelId) {
                return {
                  ...level,
                  files: [...(level.files || []), newFileMeta]
                };
              }
              return level;
            })
          };
        })
      };
    });

    setSagaData(updatedSaga);
    triggerDopamine("📎 Đính kèm tệp tài liệu thành công!", 2);
  };

  const handleDeleteStudyFile = (fileIdx) => {
    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          return {
            ...region,
            levels: region.levels.map(level => {
              if (level.id === activeLevelId) {
                return {
                  ...level,
                  files: (level.files || []).filter((_, idx) => idx !== fileIdx)
                };
              }
              return level;
            })
          };
        })
      };
    });
    setSagaData(updatedSaga);
    playAudioFeedback('error', isMuted);
  };

  const handleGuiltFreeReschedule = () => {
    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          return {
            ...region,
            levels: region.levels.map(level => {
              if (level.id === activeLevelId) {
                const updatedTasks = level.tasks.map(t => {
                  if (!t.completed) {
                    return { ...t, text: `${t.text.replace(' (Dời lịch thảnh thơi 💤)', '')} (Dời lịch thảnh thơi 💤)` };
                  }
                  return t;
                });
                return { ...level, tasks: updatedTasks };
              }
              return level;
            })
          };
        })
      };
    });
    setSagaData(updatedSaga);
    triggerDopamine("Lịch trình đã tự động giãn nở. Hãy nhâm nhi tách trà và học thảnh thơi nhé! 🥰☕", 3);
  };

  // Quản lý Môn học (Đất nước) & Kỹ năng (Vùng đất)
  const handleAddCountry = (e) => {
    e.preventDefault();
    if (!newCountryName.trim()) return;
    const newId = `subject-${Date.now()}`;
    const newCountry = {
      id: newId,
      name: newCountryName,
      month: newCountryMonth || 'Mục tiêu học phần',
      emoji: '📚',
      regions: []
    };
    setSagaData([...sagaData, newCountry]);
    setActiveCountryId(newId);
    setNewCountryName('');
    setNewCountryMonth('');
    triggerDopamine(`📚 Đã khởi tạo môn học mục tiêu mới "${newCountryName}"!`, 3);
  };

  const handleAddRegion = (e) => {
    e.preventDefault();
    if (!newRegionName.trim()) return;
    const newRegId = `skill-${Date.now()}`;
    const newReg = {
      id: newRegId,
      name: newRegionName,
      description: newRegionDesc || 'Kỹ năng cần bổ trợ',
      color: ['from-purple-500 to-pink-600', 'from-cyan-500 to-blue-600', 'from-yellow-400 to-amber-600'][Math.floor(Math.random() * 3)],
      level: 1, // Bắt đầu ở Level 1
      xp: 0,    // Bắt đầu ở 0 XP
      streak: 0, // Bắt đầu ở 0 ngày liên tiếp
      goals: {
        longTerm: '',
        shortTerm: '',
        reason: '',
        deadline: '',
        dreamVersion: ''
      },
      roadmap: [],
      levels: [
        { id: `lvl-${Date.now()}-1`, num: 1, name: 'Ngày 1', x: 12, y: 75, tasks: [], links: [], files: [] },
        { id: `lvl-${Date.now()}-2`, num: 2, name: 'Ngày 2', x: 32, y: 35, tasks: [], links: [], files: [] },
        { id: `lvl-${Date.now()}-3`, num: 3, name: 'Ngày 3', x: 52, y: 68, tasks: [], links: [], files: [] },
        { id: `lvl-${Date.now()}-4`, num: 4, name: 'Ngày 4', x: 72, y: 30, tasks: [], links: [], files: [] },
        { id: `lvl-${Date.now()}-5`, num: 5, name: 'Ngày 5', x: 90, y: 65, tasks: [], links: [], files: [] }
      ]
    };

    setSagaData(sagaData.map(c => {
      if (c.id === activeCountryId) {
        return { ...c, regions: [...c.regions, newReg] };
      }
      return c;
    }));
    setActiveRegionId(newRegId);
    setNewRegionName('');
    setNewRegionDesc('');
    triggerDopamine(`🗺️ Đã tạo học phần kỹ năng "${newRegionName}" cho môn này!`, 3);
  };

  // Cập nhật Goals (Mục tiêu)
  const handleUpdateGoalField = (field, value) => {
    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          if (region.id === activeRegionId) {
            return {
              ...region,
              goals: {
                ...(region.goals || { longTerm: '', shortTerm: '', reason: '', deadline: '', dreamVersion: '' }),
                [field]: value
              }
            };
          }
          return region;
        })
      };
    });
    setSagaData(updatedSaga);
  };

  // Quản lý Roadmap Milestones
  const handleAddMilestone = (e) => {
    e.preventDefault();
    if (!newMilestoneText.trim()) return;

    const newMilestone = {
      id: `m-${Date.now()}`,
      text: newMilestoneText,
      completed: false
    };

    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          if (region.id === activeRegionId) {
            return {
              ...region,
              roadmap: [...(region.roadmap || []), newMilestone]
            };
          }
          return region;
        })
      };
    });

    setSagaData(updatedSaga);
    setNewMilestoneText('');
    playAudioFeedback('click', isMuted);
  };

  const handleToggleMilestone = (milestoneId) => {
    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          if (region.id === activeRegionId) {
            const updatedRoadmap = (region.roadmap || []).map(m => {
              if (m.id === milestoneId) {
                const nextVal = !m.completed;
                if (nextVal) {
                  playAudioFeedback('success', isMuted);
                  gainXP(30); // Check thành công mốc học tập nhận +30 XP
                }
                return { ...m, completed: nextVal };
              }
              return m;
            });
            return {
              ...region,
              roadmap: updatedRoadmap
            };
          }
          return region;
        })
      };
    });
    setSagaData(updatedSaga);
  };

  const handleDeleteMilestone = (milestoneId) => {
    const updatedSaga = sagaData.map(country => {
      return {
        ...country,
        regions: country.regions.map(region => {
          if (region.id === activeRegionId) {
            return {
              ...region,
              roadmap: (region.roadmap || []).filter(m => m.id !== milestoneId)
            };
          }
          return region;
        })
      };
    });
    setSagaData(updatedSaga);
    playAudioFeedback('error', isMuted);
  };

  // Quản lý Ghi chú (Notes)
  const handleAddNote = (e) => {
    e.preventDefault();
    if (!newNoteTitle.trim() || !newNoteContent.trim()) return;

    const newNote = {
      id: `note-${Date.now()}`,
      title: newNoteTitle,
      content: newNoteContent,
      date: new Date().toLocaleDateString('vi-VN'),
      color: newNoteColor
    };

    const currentRegionNotes = notesByRegion[activeRegionId] || [];
    setNotesByRegion({
      ...notesByRegion,
      [activeRegionId]: [newNote, ...currentRegionNotes]
    });

    setNewNoteTitle('');
    setNewNoteContent('');
    triggerDopamine(`🌱 Lưu thành công ghi chú vào học phần này!`, 3);
  };

  const handleDeleteNote = (noteId) => {
    const currentRegionNotes = notesByRegion[activeRegionId] || [];
    setNotesByRegion({
      ...notesByRegion,
      [activeRegionId]: currentRegionNotes.filter(n => n.id !== noteId)
    });
    playAudioFeedback('error', isMuted);
  };

  // Quản lý Flashcards & Matching
  const handleCreateCustomFlashcard = (e) => {
    e.preventDefault();
    if (!newCardQ.trim() || !newCardA.trim()) return;

    const optionsList = [
      newCardA, 
      newCardOpt2.trim() || 'Lựa chọn nhiễu A',
      newCardOpt3.trim() || 'Lựa chọn nhiễu B',
      newCardOpt4.trim() || 'Lựa chọn nhiễu C'
    ];

    const newCard = {
      id: Date.now(),
      q: newCardQ,
      a: newCardA,
      options: optionsList.sort(() => Math.random() - 0.5),
      flipped: false
    };

    const currentCards = flashcardsByRegion[activeRegionId] || [];
    setFlashcardsByRegion({
      ...flashcardsByRegion,
      [activeRegionId]: [newCard, ...currentCards]
    });

    setNewCardQ('');
    setNewCardA('');
    setNewCardOpt2('');
    setNewCardOpt3('');
    setNewCardOpt4('');
    triggerDopamine("Thẻ bài tự tạo đã được thêm vào học phần! 🃏", 3);
  };

  const handleAddManualTerm = (e) => {
    e.preventDefault();
    if (!newTermText.trim() || !newDefText.trim()) return;
    const matchId = `m-${Date.now()}`;
    const newTerm = { id: `t-${Date.now()}`, text: newTermText, matchId };
    const newDef = { id: `d-${Date.now()}`, text: newDefText, matchId };
    
    const currentTerms = matchingTermsByRegion[activeRegionId] || [];
    const currentDefs = matchingDefsByRegion[activeRegionId] || [];

    setMatchingTermsByRegion({
      ...matchingTermsByRegion,
      [activeRegionId]: [...currentTerms, newTerm]
    });

    setMatchingDefsByRegion({
      ...matchingDefsByRegion,
      [activeRegionId]: [...currentDefs, newDef]
    });

    setNewTermText('');
    setNewDefText('');
    triggerDopamine("Cặp nối mới đã sẵn sàng cho học phần này! 🧩", 3);
  };

  const resetMatchGame = () => {
    setSelectedTerm(null);
    setSelectedDef(null);
    setMatchedPairs([]);
    setMatchGameStatus('Hãy chọn một thuật ngữ ở cột trái rồi tìm định nghĩa đúng ở cột phải nhé! 🐾');
  };

  const handleTermSelect = (term) => {
    if (matchedPairs.includes(term.matchId)) return;
    playAudioFeedback('click', isMuted);
    if (selectedTerm?.id === term.id) {
      setSelectedTerm(null);
      return;
    }
    setSelectedTerm(term);
    if (selectedDef) checkMatch(term, selectedDef);
  };

  const handleDefSelect = (def) => {
    if (matchedPairs.includes(def.matchId)) return;
    playAudioFeedback('click', isMuted);
    if (selectedDef?.id === def.id) {
      setSelectedDef(null);
      return;
    }
    setSelectedDef(def);
    if (selectedTerm) checkMatch(selectedTerm, def);
  };

  const checkMatch = (term, def) => {
    if (term.matchId === def.matchId) {
      const updatedPairs = [...matchedPairs, term.matchId];
      setMatchedPairs(updatedPairs);
      setSelectedTerm(null);
      setSelectedDef(null);
      setMatchGameStatus('Chính xác! Một liên kết tuyệt vời! 🌟🦴');
      playAudioFeedback('success', isMuted);
      
      const currentTerms = matchingTermsByRegion[activeRegionId] || [];
      if (updatedPairs.length === currentTerms.length) {
        triggerDopamine("Chúc mừng! Bạn đã hoàn thành toàn bộ trò chơi nối ghép thuật ngữ! 🏆🧠", 5, true);
        gainXP(150); // Hoàn thành game Nối Cặp được thưởng 150 XP
      }
    } else {
      setMatchGameStatus('Ui da! Cặp nối này chưa đúng rồi, thử lại nhé! 🤔');
      playAudioFeedback('error', isMuted);
      setTimeout(() => {
        setSelectedTerm(null);
        setSelectedDef(null);
      }, 800);
    }
  };

  // Quản lý Giáo án Thể chất (Workout Tracker)
  const handleAddWorkoutRoutine = (e) => {
    e.preventDefault();
    if (!newWorkoutName.trim()) return;

    const newRoutine = {
      id: `workout-${Date.now()}`,
      name: newWorkoutName,
      sets: newWorkoutSets || '1 hiệp',
      reps: newWorkoutReps || 'Mục tiêu tự do',
      link: newWorkoutLink.trim(),
      completed: false
    };

    setWorkoutRoutines([...workoutRoutines, newRoutine]);
    setNewWorkoutName('');
    setNewWorkoutSets('');
    setNewWorkoutReps('');
    setNewWorkoutLink('');
    triggerDopamine("🏋️‍♂️ Đã thêm bài tập thể chất mới thành công!", 3);
  };

  const handleToggleWorkout = (routineId) => {
    const updated = workoutRoutines.map(w => {
      if (w.id === routineId) {
        const nextVal = !w.completed;
        if (nextVal) {
          playAudioFeedback('success', isMuted);
          gainXP(20); // Tập thể dục được tích lũy 20 XP
        }
        return { ...w, completed: nextVal };
      }
      return w;
    });
    setWorkoutRoutines(updated);
  };

  const handleDeleteWorkout = (routineId) => {
    setWorkoutRoutines(workoutRoutines.filter(w => w.id !== routineId));
    playAudioFeedback('error', isMuted);
  };

  // Quản lý Nhật ký
  const handleImageChange = (e) => {
    const file = e.target.files[0];
    if (file) {
      const reader = new FileReader();
      reader.onloadend = () => {
        setJournalImagePreview(reader.result);
      };
      reader.readAsDataURL(file);
    }
  };

  const handleAddJournalEntry = (e) => {
    e.preventDefault();
    if (!newJournalText.trim()) return;

    const newEntry = {
      id: Date.now(),
      date: new Date().toLocaleDateString('vi-VN'),
      mood: newJournalMood,
      text: newJournalText,
      image: journalImagePreview
    };

    setJournalEntries([newEntry, ...journalEntries]);
    setNewJournalText('');
    setJournalImagePreview(null);
    if (fileInputRef.current) fileInputRef.current.value = '';
    
    triggerDopamine("Đã lưu kỷ niệm vào sổ nhật ký thành công! 📔✨", 3);
  };

  const adjustWater = (amount) => {
    setWaterGlasses(prev => {
      const nextVal = Math.min(Math.max(prev + amount, 0), targetWaterGlasses);
      if (nextVal > prev) {
        playAudioFeedback('click', isMuted);
        gainXP(5); // Mỗi cốc nước được +5 XP
      } else {
        playAudioFeedback('error', isMuted);
      }
      if (nextVal === targetWaterGlasses && prev < targetWaterGlasses) {
        triggerDopamine("Cơ thể đủ nước rồi! Trao đổi chất cực nhanh luôn! 🐳💧", 3, true);
      }
      return nextVal;
    });
  };

  const callGeminiAPI = async (prompt, systemInstruction = "") => {
    const apiKey = aiApiKey; 
    const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;
    
    const payload = {
      contents: [{ parts: [{ text: prompt }] }],
      ...(systemInstruction ? { systemInstruction: { parts: [{ text: systemInstruction }] } } : {})
    };

    try {
      const response = await fetch(apiUrl, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(payload)
      });
      const result = await response.json();
      return result.candidates?.[0]?.content?.parts?.[0]?.text || null;
    } catch (e) {
      console.error("Gemini API error:", e);
      return null;
    }
  };

  const handleAiChatSubmit = async (e) => {
    e.preventDefault();
    if (!aiPrompt.trim()) return;

    const userMessage = aiPrompt;
    setAiChatHistory(prev => [...prev, { role: 'user', text: userMessage }]);
    setAiPrompt('');
    setIsAiLoading(true);
    playAudioFeedback('click', isMuted);

    const systemPrompt = "Bạn là chú chó thông minh Snoopy AI, đồng hành của người mắc ADHD. Hãy trò chuyện ngắn gọn, vui tươi, sử dụng nhiều emoji dễ thương, tuyệt đối không giáo điều.";
    const aiText = await callGeminiAPI(userMessage, systemPrompt);

    if (aiText) {
      setAiChatHistory(prev => [...prev, { role: 'model', text: aiText }]);
      playAudioFeedback('success', isMuted);
    } else {
      setAiChatHistory(prev => [...prev, { role: 'model', text: 'Gâu gâu! Kết nối với trạm phát sóng Snoopy gặp chút lỗi nhỏ. Hãy thở sâu rồi thử lại bạn nhé!' }]);
      playAudioFeedback('error', isMuted);
    }
    setIsAiLoading(false);
  };

  // AI Planner: Sắp xếp thời khóa biểu thông minh tránh Burnout
  const handleAiPlanSchedule = async () => {
    setIsPlannerLoading(true);
    playAudioFeedback('click', isMuted);

    const activeSkillName = sagaData.find(c => c.id === activeCountryId)?.regions?.find(r => r.id === activeRegionId)?.name || 'Kỹ năng chưa chọn';
    const userPrompt = `Tôi bị ADHD và muốn học kỹ năng: "${activeSkillName}". Thời gian rảnh trong ngày: ${plannerFreeHours}. Thời gian cần học gấp/Deadline: ${plannerDeadline}. Mức độ ưu tiên: ${plannerPriority}. Hãy đề xuất một lịch học tối ưu chia thành các khối sáng/chiều/tối xen kẽ thời gian nghỉ cụ thể (VD: 15p, 20p) để bộ não ADHD của tôi không bị quá tải (Avoid Burnout). Phản hồi dưới dạng JSON Array có cấu trúc: [{"time": "...", "activity": "...", "break": "..."}]. Hãy chỉ trả về duy nhất chuỗi JSON để tôi parse, không thêm text giải thích nào khác.`;
    
    const response = await callGeminiAPI(userPrompt, "Bạn là chuyên gia thiết kế lịch học cho học sinh ADHD.");
    
    if (response) {
      try {
        // Tìm và parse JSON từ response đề phòng AI thêm markdown codeblock ```json
        const jsonMatch = response.match(/\[[\s\S]*\]/);
        if (jsonMatch) {
          const parsed = JSON.parse(jsonMatch[0]);
          setPlannerSuggestedSchedule(parsed);
          triggerDopamine("📅 Snoopy AI đã thiết lập xong thời khóa biểu thảnh thơi chống Burnout!", 3);
        } else {
          // Fallback nếu parse lỗi
          throw new Error("Cannot find JSON array");
        }
      } catch (err) {
        console.warn("Failed parsing AI Planner response, using smart local rule fallback:", err);
        generateLocalSmartSchedule();
      }
    } else {
      generateLocalSmartSchedule();
    }
    setIsPlannerLoading(false);
  };

  const generateLocalSmartSchedule = () => {
    // Thuật toán đề xuất lịch học tự động offline
    const fallbackSchedule = [
      { time: 'Sáng (09:00 - 10:15)', activity: `Học lý thuyết cốt lõi về ${sagaData.find(c => c.id === activeCountryId)?.regions?.find(r => r.id === activeRegionId)?.name || 'Kỹ năng'}`, break: '15 phút giải lao' },
      { time: 'Chiều (14:30 - 15:30)', activity: 'Thực hành nối cặp hoặc làm Todo-list ngày', break: '10 phút hít thở' },
      { time: 'Tối (20:00 - 20:45)', activity: 'Lật flashcard ghi nhớ nhanh trước khi ngủ', break: 'Nghỉ ngơi hoàn toàn 💤' }
    ];
    setPlannerSuggestedSchedule(fallbackSchedule);
    triggerDopamine("💡 Lịch học thảnh thơi tự động đã được kích hoạt!", 3);
  };

  const handleAiDietAdvise = async () => {
    setIsAiDietLoading(true);
    playAudioFeedback('click', isMuted);

    const userPrompt = `Tôi cao ${height}cm, nặng ${weight}kg, cân nặng mục tiêu là ${targetWeight}kg. Chỉ số BMI của tôi là ${bmi}. Tôi muốn giảm cân an toàn và tôi bị hội chứng ADHD. Hãy viết thực đơn thảnh thơi, dễ nấu, giàu dinh dưỡng cho tôi.`;
    const systemPrompt = "Bạn là Snoopy AI, chuyên gia dinh dưỡng cá nhân hóa hỗ trợ học sinh có ADHD xây dựng thói quen ăn uống giảm cân lành mạnh.";

    const response = await callGeminiAPI(userPrompt, systemPrompt);

    if (response) {
      setDietSuggestion(response);
      triggerDopamine("🍉 Đã nhận thực đơn tập luyện và dinh dưỡng từ Snoopy AI!", 3);
    } else {
      setDietSuggestion("Có lỗi xảy ra khi gọi AI. Hãy bổ sung thật nhiều rau củ tươi và dắt cún đi bộ 15 phút nha!");
    }
    setIsAiDietLoading(false);
  };

  const handleAddLockNote = (e) => {
    e.preventDefault();
    if (!newLockNote.trim()) return;
    setLockscreenNotes([...lockscreenNotes, { id: Date.now(), text: newLockNote, pinned: true }]);
    setNewLockNote('');
    playAudioFeedback('click', isMuted);
  };

  if (!activeRoom) {
    return (
      <div className="min-h-screen bg-[#61804E] text-slate-900 font-sans p-4 flex flex-col items-center justify-center relative overflow-hidden"
           style={{
             backgroundImage: `
               linear-gradient(to right, rgba(255, 255, 255, 0.12) 1px, transparent 1px),
               linear-gradient(to bottom, rgba(255, 255, 255, 0.12) 1px, transparent 1px)
             `,
             backgroundSize: '24px 24px'
           }}>
        
        <div className="absolute -top-12 -left-12 w-64 h-64 bg-amber-400 rounded-full border-4 border-black opacity-30 animate-pulse"></div>

        <div className="max-w-md w-full bg-white rounded-[3rem] border-8 border-black p-8 shadow-[12px_12px_0_0_#000] space-y-6 text-center relative z-10 transform hover:scale-[1.01] transition-transform">
          
          <div className="w-24 h-24 bg-red-500 rounded-2xl border-4 border-black mx-auto flex items-center justify-center shadow-[4px_4px_0_0_#000] relative group">
            <span className="text-5xl group-hover:animate-bounce">🐶</span>
            <div className="absolute -top-3 -right-3 bg-yellow-300 border-2 border-black rounded-full p-1 text-xs">🔒</div>
          </div>

          <div className="space-y-1">
            <h1 className="text-3xl font-black tracking-tight text-slate-900">Snoopy's Gate 🐾</h1>
            <p className="text-xs font-bold text-slate-500 max-w-xs mx-auto">
              Không gian cá nhân hóa lưu trữ đám mây an toàn. Hãy nhập phòng riêng của bạn để bắt đầu!
            </p>
          </div>

          <div className="bg-slate-100 px-3 py-1.5 rounded-xl border border-slate-300 text-[10px] font-black text-slate-700 inline-flex items-center gap-1">
            <Database size={12} className="text-emerald-500 animate-pulse" />
            <span>Trạng thái máy chủ:</span>
            <span className="text-emerald-700">{syncStatus}</span>
          </div>

          {cloudError && (
            <div className="bg-red-50 border-2 border-red-500 text-red-700 px-4 py-2 rounded-xl text-xs font-black leading-snug">
              ⚠️ {cloudError}
            </div>
          )}

          <div className="space-y-4">
            <div className="space-y-2">
              <div className="bg-slate-50 p-3 rounded-2xl border-2 border-black flex items-center gap-2">
                <Globe size={16} className="text-slate-500" />
                <input 
                  type="text" 
                  placeholder="Tên Phòng (ví dụ: math2026, ielts_an)"
                  value={workspaceNameInput}
                  onChange={e => setWorkspaceNameInput(e.target.value.toLowerCase().trim())}
                  className="w-full bg-transparent border-none text-xs font-black focus:outline-none placeholder-slate-400 text-center"
                />
              </div>

              <div className="bg-slate-50 p-3 rounded-2xl border-2 border-black flex items-center gap-2">
                <Key size={16} className="text-slate-500" />
                <input 
                  type="password" 
                  placeholder="Nhập Mật Khẩu Bảo Mật..."
                  value={roomPasscode}
                  onChange={e => setRoomPasscode(e.target.value)}
                  className="w-full bg-transparent border-none text-xs font-black focus:outline-none placeholder-slate-400 text-center"
                />
              </div>
            </div>

            <div className="grid grid-cols-2 gap-3 pt-2">
              <button
                onClick={handleLoginWorkspace}
                disabled={isCloudLoading}
                className="bg-yellow-300 hover:bg-yellow-400 text-slate-900 border-4 border-black font-black py-3 rounded-2xl text-xs shadow-[3px_3px_0_0_#000] active:translate-x-0.5 active:translate-y-0.5 active:shadow-[1px_1px_0_0_#000] transition-all disabled:opacity-50"
              >
                {isCloudLoading ? 'ĐANG TẢI...' : 'ĐĂNG NHẬP 🔑'}
              </button>

              <button
                onClick={handleRegisterWorkspace}
                disabled={isCloudLoading}
                className="bg-emerald-300 hover:bg-emerald-400 text-slate-900 border-4 border-black font-black py-3 rounded-2xl text-xs shadow-[3px_3px_0_0_#000] active:translate-x-0.5 active:translate-y-0.5 active:shadow-[1px_1px_0_0_#000] transition-all disabled:opacity-50"
              >
                {isCloudLoading ? 'ĐANG TẠO...' : 'TẠO PHÒNG MỚI 🌱'}
              </button>
            </div>
          </div>

          <div className="border-t-2 border-dashed border-slate-200 pt-4 text-left">
            <details className="group">
              <summary className="text-[10px] font-black text-slate-500 cursor-pointer list-none flex items-center justify-between">
                <span className="flex items-center gap-1 hover:underline"><ShieldCheck size={12}/> Thiết lập Cloud Database cá nhân của riêng bạn?</span>
                <span className="transition-transform group-open:rotate-180">▼</span>
              </summary>
              <form onSubmit={handleSaveCustomConfig} className="space-y-2 mt-3 bg-slate-50 p-3 rounded-xl border border-slate-200">
                <p className="text-[9px] font-bold text-slate-500 leading-relaxed">
                  Dán chuỗi cấu hình `firebaseConfig` của bạn vào ô dưới đây để tạo một database biệt lập chỉ mình bạn sở hữu:
                </p>
                <textarea 
                  rows="5"
                  placeholder='{ "apiKey": "...", "projectId": "..." }'
                  value={dbConfigInput}
                  onChange={e => setDbConfigInput(e.target.value)}
                  className="w-full bg-white border border-slate-300 rounded-lg p-2 font-mono text-[9px] text-slate-700 focus:outline-none"
                />
                <div className="flex gap-2">
                  <button type="submit" className="flex-1 bg-slate-900 text-white text-[9px] font-black py-1.5 rounded-lg">Lưu cấu hình</button>
                  <button type="button" onClick={handleResetConfigToDefault} className="bg-slate-200 text-slate-700 text-[9px] font-black py-1.5 px-3 rounded-lg">Khôi phục mặc định</button>
                </div>
              </form>
            </details>
          </div>

        </div>
      </div>
    );
  }

  return (
    <div className="min-h-screen bg-[#61804E] text-slate-900 font-sans p-3 md:p-8 relative overflow-x-hidden selection:bg-yellow-200 pb-24"
         style={{
           backgroundImage: `
             linear-gradient(to right, rgba(255, 255, 255, 0.12) 1px, transparent 1px),
             linear-gradient(to bottom, rgba(255, 255, 255, 0.12) 1px, transparent 1px)
           `,
           backgroundSize: '24px 24px'
         }}>
      
      {confettiActive && (
        <div className="fixed inset-0 pointer-events-none z-50 overflow-hidden">
          {Array.from({ length: 45 }).map((_, i) => {
            const randomX = Math.random() * 100;
            const randomColor = ['bg-yellow-400', 'bg-blue-400', 'bg-pink-400', 'bg-emerald-400', 'bg-purple-400'][Math.floor(Math.random() * 5)];
            return (
              <div 
                key={i} 
                className={`absolute w-3 h-3 rounded-full ${randomColor} animate-bounce opacity-80`}
                style={{
                  left: `${randomX}%`,
                  top: `-10px`,
                  animationDuration: `${1 + Math.random() * 1.5}s`,
                  transform: `scale(${0.5 + Math.random() * 1.2})`
                }}
              />
            );
          })}
        </div>
      )}

      {/* RPG LEVEL UP POPUP OVERLAY */}
      {levelUpAlert && (
        <div className="fixed inset-0 z-50 bg-black/60 flex items-center justify-center p-4 backdrop-blur-sm">
          <div className="bg-[#FEF08A] border-8 border-black p-8 rounded-[3.5rem] shadow-[12px_12px_0_0_#000] text-center max-w-md w-full relative animate-bounce">
            <span className="text-7xl block mb-3 animate-pulse">👑🏆🦖</span>
            <h2 className="text-3xl font-black tracking-tight text-slate-900 mb-2">SNOOPY LEVEL UP!</h2>
            <p className="text-sm font-black text-slate-700 leading-relaxed">
              Tuyệt đỉnh! Kỹ năng <strong className="text-indigo-700 font-black">"{levelUpAlert.skillName}"</strong> của bạn đã đột phá thăng lên:
            </p>
            <div className="my-5 inline-block bg-white text-slate-900 border-4 border-black px-6 py-2.5 rounded-2xl text-2xl font-black shadow-[4px_4px_0_0_#000]">
              🌟 LEVEL {levelUpAlert.level} 🌟
            </div>
            <p className="text-xs font-bold text-slate-500">
              Hãy tiếp tục tích lũy XP bằng cách học tập và uống nước nhé. Dino đang reo hò vì bạn! 🐾
            </p>
            <button 
              onClick={() => { setLevelUpAlert(null); playAudioFeedback('click', isMuted); }}
              className="mt-6 bg-slate-900 hover:bg-slate-800 text-white font-black py-2.5 px-6 rounded-xl border-2 border-black text-xs shadow-[2px_2px_0_0_#000] active:translate-y-0.5"
            >
              Nhận Thưởng & Tiếp Tục 🦴
            </button>
          </div>
        </div>
      )}

      {dopamineAlert && (
        <div className="fixed inset-x-0 top-6 z-50 flex justify-center items-center pointer-events-none px-4">
          <div className="bg-[#FEF08A] border-4 border-black px-6 py-5 rounded-[2rem] shadow-[6px_6px_0_0_#000] max-w-md text-center flex flex-col items-center gap-3 relative z-50">
            <div className="flex gap-1.5 justify-center">
              <Star className="text-orange-500 fill-orange-500 animate-pulse" size={24} />
              <Star className="text-orange-500 fill-orange-500 animate-bounce" size={24} />
              <Star className="text-orange-500 fill-orange-500 animate-pulse" size={24} />
            </div>
            
            <p className="font-black text-slate-900 text-sm md:text-base leading-snug">
              {dopamineAlert.message}
            </p>

            <div className="bg-white/70 px-4 py-1.5 rounded-full border border-black/10 font-black text-slate-700 flex items-center gap-1.5 text-xs">
              <Zap size={14} className="fill-orange-400 text-orange-400 animate-spin"/> Dopamine Đang Tải!
            </div>
          </div>
        </div>
      )}

      <div className="max-w-7xl mx-auto space-y-6">
        
        <div className="flex flex-col md:flex-row items-center justify-between gap-3 bg-slate-900 border-4 border-black p-4 rounded-3xl shadow-[4px_4px_0_0_#000] text-white">
          <div className="flex items-center gap-2 text-xs md:text-sm font-black text-slate-100">
            <span className="w-2.5 h-2.5 rounded-full bg-emerald-400 animate-ping"></span>
            <span>Không gian riêng của bạn:</span>
            <span className="bg-yellow-300 text-slate-900 px-3 py-1 rounded-xl text-xs tracking-wider border-2 border-black">
              {activeRoom}
            </span>
          </div>

          <div className="flex items-center gap-2">
            <span className="text-[10px] md:text-xs text-slate-400 font-bold">{syncStatus}</span>
            <button 
              onClick={handleLockRoom}
              className="bg-red-400 hover:bg-red-500 text-slate-900 px-3 py-1.5 rounded-xl text-xs font-black border-2 border-black flex items-center gap-1 transition-all"
            >
              <LogOut size={12} /> Khóa phòng & Thoát
            </button>
          </div>
        </div>

        <div className="bg-yellow-50 border-4 border-black rounded-[2rem] p-4 shadow-[4px_4px_0_0_#000] flex flex-col md:flex-row items-center justify-between gap-4">
          <div className="flex items-center gap-2.5">
            <Sparkles className="text-yellow-500 fill-yellow-500 animate-pulse" size={24}/>
            <div>
              <h3 className="font-black text-xs md:text-sm text-slate-800">Cài đặt API Gemini (Không bắt buộc)</h3>
              <p className="text-[10px] font-bold text-slate-500">Mặc định đã tự động hóa. Thêm key cá nhân nếu muốn hoạt động độc lập.</p>
            </div>
          </div>
          <input 
            type="password"
            placeholder="Nhập Gemini API Key tại đây..."
            value={aiApiKey}
            onChange={(e) => setAiApiKey(e.target.value)}
            className="w-full md:w-64 bg-white border-2 border-black rounded-xl px-3 py-1.5 text-xs font-bold focus:outline-none"
          />
        </div>

        {/* Header (image_caf328.png) */}
        <header className="relative bg-white rounded-[3rem] border-4 border-black p-6 md:p-10 shadow-[8px_8px_0_0_#000] overflow-hidden flex flex-col items-center text-center">
          
          <div className="absolute top-4 left-6 text-2xl animate-pulse">✨</div>
          <div className="absolute top-12 right-12 text-3xl text-yellow-300">✨</div>
          <div className="absolute bottom-6 left-12 text-xl">🌱</div>

          {/* Sun graphics (image_cae803.png) */}
          <div className="relative w-48 h-48 md:w-56 md:h-56 bg-amber-400 rounded-full border-4 border-black shadow-inner flex items-center justify-center transform rotate-3 my-4">
            <div className="absolute -inset-2 rounded-full border-4 border-dashed border-black opacity-10 animate-spin" style={{ animationDuration: '30s' }}></div>
            <div className="relative w-full h-full flex flex-col items-center justify-center">
              <div className="flex justify-between w-20 mb-3 px-1">
                <svg className="w-6 h-6 text-black" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="4" strokeLinecap="round">
                  <path d="M4 12 Q10 17 16 12" />
                </svg>
                <div className="w-5 h-5 bg-black rounded-full"></div>
              </div>
              <svg className="w-10 h-6 text-black" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="4" strokeLinecap="round">
                <path d="M4 4 Q12 14 20 4" />
              </svg>
            </div>

            {/* Dino mascot (image_cae803.png) */}
            <div className="absolute -bottom-4 -right-12 transform scale-75 md:scale-90 hover:scale-105 transition-transform">
              <div className="bg-[#8EBC77] border-4 border-black rounded-[2rem] p-3 shadow-[4px_4px_0_0_#000] relative flex flex-col items-center">
                <div className="absolute -top-6 bg-slate-900 text-white text-[9px] px-2.5 py-0.5 rounded-lg border-2 border-black font-black">DINO CLASS</div>
                <span className="text-3xl">🦖</span>
                <span className="text-[9px] font-black bg-white border border-black px-1.5 rounded mt-1">100+ ĐỀ</span>
              </div>
            </div>
          </div>

          <div className="z-10 mt-2 space-y-2">
            <h1 className="text-4xl md:text-6xl font-black text-slate-900 tracking-tight">
              Snoopy Study Dash <span className="text-yellow-400">🐾</span>
            </h1>
            <p className="text-sm md:text-base font-bold text-slate-500 max-w-2xl mx-auto">
              Không gian cá nhân hóa rực rỡ, thiết kế đồng hành giúp người học ADHD chinh phục đỉnh cao!
            </p>
          </div>

          <div className="mt-6 w-full max-w-3xl flex flex-col items-center gap-3">
            
            <div className="bg-slate-100 px-5 py-2 rounded-full border-2 border-black text-xs font-black text-slate-700 flex items-center gap-1.5 shadow-sm">
              <span>FOLLOW SNOOPY ON</span>
              <div className="w-5 h-5 bg-blue-600 text-white rounded-full flex items-center justify-center text-[10px] font-bold">f</div>
              <div className="w-5 h-5 bg-black text-white rounded-full flex items-center justify-center text-[10px] font-bold">t</div>
            </div>

            {/* Header Quote Container (image_cb01ee.png) */}
            <div className="w-full flex items-center justify-between gap-2.5 relative">
              <div className="flex flex-col gap-1 shrink-0">
                <span className="text-2xl">🌱</span>
                <span className="text-2xl">🌱</span>
              </div>
              
              <div className="flex-1 bg-[#FEF08A] rounded-full border-4 border-black font-black p-3.5 shadow-[4px_4px_0_0_#000] flex items-center gap-2">
                <Edit3 size={16} className="text-slate-500 shrink-0" />
                <input 
                  type="text"
                  value={headerQuote}
                  onChange={(e) => setHeaderQuote(e.target.value)}
                  placeholder="Hãy gõ một châm ngôn giúp truyền động lực cho chính bạn... ✍️"
                  className="w-full bg-transparent border-none text-slate-800 text-xs md:text-sm font-black focus:outline-none placeholder-slate-500 text-center"
                />
              </div>

              <button 
                onClick={() => {
                  setIsMuted(!isMuted);
                  playAudioFeedback('click', !isMuted);
                }} 
                className="p-3 bg-white rounded-full border-4 border-black shadow-[4px_4px_0_0_#000] hover:bg-slate-50 transition-all shrink-0 flex items-center justify-center"
              >
                {isMuted ? <VolumeX size={18} strokeWidth={3} /> : <Volume2 size={18} strokeWidth={3} />}
              </button>
            </div>

          </div>
        </header>

        {/* Tab Navigation (image_cbeacd.png) */}
        <nav className="grid grid-cols-2 md:grid-cols-6 gap-3">
          <button 
            onClick={() => { setActiveTab('map'); playAudioFeedback('click', isMuted); }}
            className={`py-3.5 rounded-[2rem] border-4 border-black font-black text-xs md:text-sm transition-all flex items-center justify-center gap-2 ${activeTab === 'map' ? 'bg-[#BAE6FD] text-slate-900 shadow-[4px_4px_0_0_#000]' : 'bg-white text-slate-600 hover:bg-slate-50'}`}
          >
            <span>🗺️ Bản Đồ Lộ Trình</span>
          </button>

          <button 
            onClick={() => { setActiveTab('notes'); playAudioFeedback('click', isMuted); }}
            className={`py-3.5 rounded-[2rem] border-4 border-black font-black text-xs md:text-sm transition-all flex items-center justify-center gap-2 ${activeTab === 'notes' ? 'bg-[#FED7AA] text-slate-900 shadow-[4px_4px_0_0_#000]' : 'bg-white text-slate-600 hover:bg-slate-50'}`}
          >
            <FileText size={16} strokeWidth={3} />
            <span>Ghi Chú 🌱</span>
          </button>

          <button 
            onClick={() => { setActiveTab('review'); playAudioFeedback('click', isMuted); }}
            className={`py-3.5 rounded-[2rem] border-4 border-black font-black text-xs md:text-sm transition-all flex items-center justify-center gap-2 ${activeTab === 'review' ? 'bg-[#FBCFE8] text-slate-900 shadow-[4px_4px_0_0_#000]' : 'bg-white text-slate-600 hover:bg-slate-50'}`}
          >
            <span>🧩 Ôn Tập Học Phần</span>
          </button>

          <button 
            onClick={() => { setActiveTab('health'); playAudioFeedback('click', isMuted); }}
            className={`py-3.5 rounded-[2rem] border-4 border-black font-black text-xs md:text-sm transition-all flex items-center justify-center gap-2 ${activeTab === 'health' ? 'bg-[#A7F3D0] text-slate-900 shadow-[4px_4px_0_0_#000]' : 'bg-white text-slate-600 hover:bg-slate-50'}`}
          >
            <span>🥗 Sức Khỏe & Thể Chất</span>
          </button>

          <button 
            onClick={() => { setActiveTab('motivation'); playAudioFeedback('click', isMuted); }}
            className={`py-3.5 rounded-[2rem] border-4 border-black font-black text-xs md:text-sm transition-all flex items-center justify-center gap-2 ${activeTab === 'motivation' ? 'bg-[#FDE047] text-slate-900 shadow-[4px_4px_0_0_#000]' : 'bg-white text-slate-600 hover:bg-slate-50'}`}
          >
            <Camera size={16} strokeWidth={3} />
            <span>Nhật Ký Động Lực</span>
          </button>

          <button 
            onClick={() => { setActiveTab('lockscreen'); playAudioFeedback('click', isMuted); }}
            className={`col-span-2 md:col-span-1 py-3.5 rounded-[2rem] border-4 border-black font-black text-xs md:text-sm transition-all flex items-center justify-center gap-2 ${activeTab === 'lockscreen' ? 'bg-[#DDD6FE] text-slate-900 shadow-[4px_4px_0_0_#000]' : 'bg-white text-slate-600 hover:bg-slate-50'}`}
          >
            <Lock size={16} strokeWidth={3} />
            <span>Màn Hình Khóa</span>
          </button>
        </nav>

        {/* Main Tab Switcher */}
        <main className="space-y-6">
          
          {activeTab === 'map' && (
            <div className="grid grid-cols-1 lg:grid-cols-12 gap-6">
              
              <div className="lg:col-span-8 space-y-6">
                
                {/* 1. Chọn Môn Học (Subject) */}
                <section className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-3">
                  <div className="flex justify-between items-center border-b-2 border-dashed border-slate-100 pb-2">
                    <h3 className="font-black text-sm flex items-center gap-1.5 text-slate-900">
                      <BookOpen size={18} className="text-blue-500 animate-pulse" /> 1. Chọn Môn Học (Ví dụ: Tiếng Nhật, Toán,...)
                    </h3>
                  </div>

                  <div className="flex flex-wrap gap-2">
                    {sagaData.map(country => (
                      <button
                        key={country.id}
                        onClick={() => {
                          setActiveCountryId(country.id);
                          if (country.regions && country.regions.length > 0) {
                            setActiveRegionId(country.regions[0].id);
                            if (country.regions[0].levels && country.regions[0].levels.length > 0) {
                              setActiveLevelId(country.regions[0].levels[0].id);
                            }
                          }
                          playAudioFeedback('click', isMuted);
                        }}
                        className={`px-4 py-2.5 rounded-2xl border-2 border-black font-black text-xs transition-all flex items-center gap-1.5 shadow-[2px_2px_0_0_#000] ${activeCountryId === country.id ? 'bg-amber-300 text-slate-950 scale-102 border-4' : 'bg-slate-100 text-slate-600 hover:bg-slate-50'}`}
                      >
                        <span>{country.emoji || '📚'}</span>
                        <div>
                          <span className="block text-left font-black">{country.name}</span>
                          <span className="block text-[9px] text-slate-500 font-bold">{country.month}</span>
                        </div>
                      </button>
                    ))}
                  </div>

                  <form onSubmit={handleAddCountry} className="flex gap-2 pt-2 border-t border-slate-100">
                    <input 
                      type="text" 
                      placeholder="Tên Môn học mới (VD: Tiếng Nhật N3, Toán Đại Số)..." 
                      value={newCountryName}
                      onChange={e => setNewCountryName(e.target.value)}
                      className="flex-1 font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-1.5 focus:outline-none"
                    />
                    <input 
                      type="text" 
                      placeholder="Mục tiêu môn học..." 
                      value={newCountryMonth}
                      onChange={e => setNewCountryMonth(e.target.value)}
                      className="w-48 font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-1.5 focus:outline-none"
                    />
                    <button type="submit" className="bg-blue-300 border-2 border-black hover:bg-blue-400 font-black px-4 rounded-xl text-xs">
                      + Khởi Tạo
                    </button>
                  </form>
                </section>

                {/* 2. Chọn Kỹ Năng / Học Phần (Skill / Unit) */}
                <section className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-3">
                  <h3 className="font-black text-sm flex items-center gap-1.5 text-slate-900">
                    <Map size={18} className="text-emerald-500" /> 2. Chọn Kỹ Năng / Học Phần Của Môn
                  </h3>

                  <div className="grid grid-cols-1 md:grid-cols-2 gap-3">
                    {sagaData.find(c => c.id === activeCountryId)?.regions.map(region => (
                      <button
                        key={region.id}
                        onClick={() => {
                          setActiveRegionId(region.id);
                          if (region.levels && region.levels.length > 0) {
                            setActiveLevelId(region.levels[0].id);
                          }
                          playAudioFeedback('click', isMuted);
                        }}
                        className={`p-3 rounded-2xl border-2 border-black text-left transition-all flex justify-between items-center shadow-[3px_3px_0_0_#000] ${activeRegionId === region.id ? 'bg-emerald-100 border-4 scale-[1.01]' : 'bg-slate-50 hover:bg-slate-100'}`}
                      >
                        <div>
                          <span className="block font-black text-xs text-slate-800">{region.name}</span>
                          <span className="block text-[10px] text-slate-500 font-bold">{region.description}</span>
                        </div>
                        <ChevronRight size={16} className="text-slate-500" />
                      </button>
                    ))}
                    {(!sagaData.find(c => c.id === activeCountryId)?.regions || sagaData.find(c => c.id === activeCountryId)?.regions.length === 0) && (
                      <div className="col-span-2 text-center py-4 border-2 border-dashed border-slate-200 rounded-xl">
                        <p className="text-xs font-bold text-slate-400">Môn học này chưa có kỹ năng học phần nào. Hãy thêm một học phần mới phía dưới!</p>
                      </div>
                    )}
                  </div>

                  <form onSubmit={handleAddRegion} className="flex gap-2 pt-2 border-t border-slate-100">
                    <input 
                      type="text" 
                      placeholder="Tên Học phần/Kỹ năng (VD: Luyện Nghe, Hán Tự)..." 
                      value={newRegionName}
                      onChange={e => setNewRegionName(e.target.value)}
                      className="flex-1 font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-1.5 focus:outline-none"
                    />
                    <input 
                      type="text" 
                      placeholder="Mô tả kỹ năng này..." 
                      value={newRegionDesc}
                      onChange={e => setNewRegionDesc(e.target.value)}
                      className="flex-1 font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-1.5 focus:outline-none"
                    />
                    <button type="submit" className="bg-emerald-300 border-2 border-black hover:bg-emerald-400 font-black px-4 rounded-xl text-xs">
                      + Tạo Kỹ Năng
                    </button>
                  </form>
                </section>

                {/* RPG PROGRESS PANEL & GOAL PANEL (CÁ NHÂN HÓA ADHD) */}
                {(() => {
                  const currentCountry = sagaData.find(c => c.id === activeCountryId);
                  const currentRegion = currentCountry?.regions.find(r => r.id === activeRegionId);
                  if (!currentRegion) return null;

                  const currentLevel = currentRegion.level || 1;
                  const currentXp = currentRegion.xp || 0;
                  const xpNeeded = 1000;
                  const currentStreak = currentRegion.streak || 0;
                  const currentGoals = currentRegion.goals || { longTerm: '', shortTerm: '', reason: '', deadline: '', dreamVersion: '' };

                  return (
                    <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
                      
                      {/* RPG Status Card */}
                      <section className="bg-gradient-to-br from-indigo-600 to-purple-700 text-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                        <div className="flex justify-between items-center">
                          <div className="flex items-center gap-1.5">
                            <Trophy className="text-yellow-300 animate-bounce" size={20}/>
                            <h4 className="font-black text-sm tracking-wide">CHỈ SỐ TIẾN HÓA (RPG)</h4>
                          </div>
                          <div className="bg-white/20 px-3 py-1 rounded-full border border-white/10 flex items-center gap-1">
                            <Flame className="text-orange-400 fill-orange-400 animate-pulse" size={14} />
                            <span className="text-[10px] font-black">{currentStreak} ngày streak</span>
                          </div>
                        </div>

                        <div className="text-center py-2 bg-black/20 rounded-2xl border border-white/10">
                          <span className="text-xs font-bold text-indigo-200 block uppercase tracking-wider">Kỹ năng hiện tại</span>
                          <span className="text-lg font-black tracking-tight">{currentRegion.name}</span>
                        </div>

                        <div className="space-y-1">
                          <div className="flex justify-between text-xs font-black">
                            <span>LEVEL {currentLevel}</span>
                            <span>{currentXp} / {xpNeeded} XP</span>
                          </div>
                          <div className="w-full bg-slate-900 border-2 border-black rounded-full h-5 overflow-hidden p-0.5 shadow-inner">
                            <div 
                              className="bg-gradient-to-r from-yellow-400 to-amber-500 h-full rounded-full transition-all duration-500 border border-black/10"
                              style={{ width: `${Math.min((currentXp / xpNeeded) * 100, 100)}%` }}
                            />
                          </div>
                        </div>

                        <p className="text-[10px] font-bold text-indigo-100 italic leading-relaxed">
                          🐾 Hoàn thành nhiệm vụ ở bản đồ Candy Crush bên dưới để nhận XP thăng cấp! Đột phá Level để làm Snoopy tự hào nhé!
                        </p>
                      </section>

                      {/* Goal / Mục tiêu Box */}
                      <section className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-3">
                        <h4 className="font-black text-sm text-slate-900 flex items-center gap-1.5">
                          <Star className="text-yellow-500 fill-yellow-500" size={18}/> MỤC TIÊU & SỨ MỆNH HỌC TẬP
                        </h4>

                        <div className="space-y-2 text-xs">
                          <div>
                            <label className="block text-[9px] font-black text-slate-400 uppercase">Mục tiêu dài hạn (Long-term Goal)</label>
                            <input 
                              type="text" 
                              value={currentGoals.longTerm}
                              onChange={e => handleUpdateGoalField('longTerm', e.target.value)}
                              placeholder="Ví dụ: Đạt IELTS 7.5 / Làm việc tại Nhật..."
                              className="w-full bg-slate-50 border border-slate-300 rounded-lg px-2 py-1 font-bold text-slate-800 focus:outline-none"
                            />
                          </div>

                          <div className="grid grid-cols-2 gap-2">
                            <div>
                              <label className="block text-[9px] font-black text-slate-400 uppercase">Hạn chót (Deadline)</label>
                              <input 
                                type="text" 
                                value={currentGoals.deadline}
                                onChange={e => handleUpdateGoalField('deadline', e.target.value)}
                                placeholder="Ví dụ: Tháng 12/2026..."
                                className="w-full bg-slate-50 border border-slate-300 rounded-lg px-2 py-1 font-bold text-slate-800 focus:outline-none"
                              />
                            </div>
                            <div>
                              <label className="block text-[9px] font-black text-slate-400 uppercase">Mục tiêu ngày/tuần</label>
                              <input 
                                type="text" 
                                value={currentGoals.shortTerm}
                                onChange={e => handleUpdateGoalField('shortTerm', e.target.value)}
                                placeholder="Ví dụ: Nhớ 20 từ mỗi ngày..."
                                className="w-full bg-slate-50 border border-slate-300 rounded-lg px-2 py-1 font-bold text-slate-800 focus:outline-none"
                              />
                            </div>
                          </div>

                          <div>
                            <label className="block text-[9px] font-black text-slate-400 uppercase">Lý do cốt lõi tại sao muốn đạt được?</label>
                            <input 
                              type="text" 
                              value={currentGoals.reason}
                              onChange={e => handleUpdateGoalField('reason', e.target.value)}
                              placeholder="Để có cuộc sống tốt đẹp hơn / Để đi du học..."
                              className="w-full bg-slate-50 border border-slate-300 rounded-lg px-2 py-1 font-bold text-slate-800 focus:outline-none"
                            />
                          </div>

                          <div>
                            <label className="block text-[9px] font-black text-slate-400 uppercase">Dream Version (Bạn sẽ là ai khi thành công?)</label>
                            <input 
                              type="text" 
                              value={currentGoals.dreamVersion}
                              onChange={e => handleUpdateGoalField('dreamVersion', e.target.value)}
                              placeholder="Một lập trình viên tự tin làm việc tại công ty đa quốc gia!"
                              className="w-full bg-yellow-50 border border-yellow-200 rounded-lg px-2 py-1 font-bold text-yellow-900 focus:outline-none"
                            />
                          </div>
                        </div>
                      </section>

                    </div>
                  );
                })()}

                {/* 3. Bản đồ Candy Crush Saga phân theo Ngày học (Days) */}
                {(() => {
                  const currentCountry = sagaData.find(c => c.id === activeCountryId);
                  const currentRegion = currentCountry?.regions.find(r => r.id === activeRegionId);
                  if (!currentRegion) return null;

                  return (
                    <section className="bg-[#BAE6FD] p-6 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] relative overflow-hidden">
                      <div className="flex justify-between items-center mb-4">
                        <div>
                          <h2 className="text-xl font-black text-slate-900 flex items-center gap-1.5">
                            🗺️ Bản Đồ Candy Crush Lộ Trình: {currentRegion.name}
                          </h2>
                          <p className="text-[10px] font-bold text-sky-800">Các mốc số tượng trưng cho các ngày. Nhập mốc để xem chi tiết danh sách Todo-list và đính kèm tài liệu học!</p>
                        </div>
                        <div className="bg-white border-2 border-black px-3 py-1 rounded-xl text-xs font-black text-sky-800 flex items-center gap-1 shadow-[2px_2px_0_0_#000]">
                          <Trophy size={14} className="text-yellow-500 fill-yellow-500" />
                          Ngày đã mở: {unlockedLevelNum}
                        </div>
                      </div>

                      <div className="bg-[#FFFDF5] rounded-3xl border-4 border-black h-96 relative overflow-hidden p-6 shadow-inner flex items-center justify-center">
                        <svg className="absolute inset-0 w-full h-full pointer-events-none" xmlns="http://www.w3.org/2000/svg">
                          <path 
                            d="M 50 280 C 120 280, 150 150, 250 150 C 350 150, 320 250, 420 250 C 520 250, 500 120, 600 120 C 700 120, 750 220, 850 220" 
                            fill="none" 
                            stroke="#94A3B8" 
                            strokeWidth="6" 
                            strokeDasharray="12 12" 
                          />
                        </svg>

                        {(currentRegion.levels || []).map(node => {
                          const isUnlocked = node.num <= unlockedLevelNum;
                          const isCurrent = node.id === activeLevelId;
                          const isPassed = node.num < unlockedLevelNum;

                          return (
                            <button
                              key={node.id}
                              onClick={() => {
                                setActiveLevelId(node.id);
                                playAudioFeedback('click', isMuted);
                              }}
                              className={`absolute w-14 h-14 rounded-full border-4 font-black text-xl flex items-center justify-center transition-all ${
                                isPassed 
                                ? 'bg-emerald-400 border-black text-black shadow-[2px_2px_0_0_#000]' 
                                : isCurrent 
                                ? 'bg-yellow-400 border-black scale-110 shadow-[4px_4px_0_0_#000] animate-pulse z-10' 
                                : isUnlocked 
                                ? 'bg-sky-300 border-black shadow-[2px_2px_0_0_#000]' 
                                : 'bg-slate-200 border-slate-400 text-slate-400 cursor-not-allowed opacity-70'
                              }`}
                              style={{ left: `${node.x}%`, top: `${node.y}%`, transform: 'translate(-50%, -50%)' }}
                              disabled={!isUnlocked}
                              title={node.name}
                            >
                              {isPassed ? '✓' : node.num}
                              <div className="absolute -bottom-7 bg-white px-1.5 py-0.5 rounded border border-black text-[8px] font-black whitespace-nowrap shadow-sm text-slate-800">
                                {node.name}
                              </div>
                              {isCurrent && (
                                <div className="absolute -top-12 animate-bounce">
                                  <span className="text-2xl">🐶</span>
                                </div>
                              )}
                            </button>
                          );
                        })}
                      </div>
                    </section>
                  );
                })()}

                {/* MILESTONE ROADMAP PATH TRACKER FOR EVERY SKILL */}
                {(() => {
                  const currentCountry = sagaData.find(c => c.id === activeCountryId);
                  const currentRegion = currentCountry?.regions.find(r => r.id === activeRegionId);
                  if (!currentRegion) return null;

                  const roadmap = currentRegion.roadmap || [];
                  const completedCount = roadmap.filter(m => m.completed).length;
                  const totalCount = roadmap.length;
                  const progressPct = totalCount > 0 ? Math.round((completedCount / totalCount) * 100) : 0;

                  return (
                    <section className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                      <div className="flex justify-between items-center border-b border-slate-100 pb-2">
                        <div>
                          <h3 className="font-black text-sm text-slate-900 flex items-center gap-1.5">
                            <CheckSquare className="text-indigo-600 animate-pulse" size={18}/> ROADMAP CỘT MỐC LỘ TRÌNH CHI TIẾT
                          </h3>
                          <p className="text-[10px] text-slate-400 font-bold">Lập ra các nấc thang học tập để chinh phục từng nấc của kỹ năng!</p>
                        </div>
                        <span className="bg-indigo-100 text-indigo-800 text-xs font-black px-2.5 py-1 rounded-xl border border-indigo-200">
                          {completedCount}/{totalCount} Cột Mốc ({progressPct}%)
                        </span>
                      </div>

                      {/* Progress Bar */}
                      <div className="w-full bg-slate-100 border border-slate-300 rounded-full h-4 overflow-hidden p-0.5 shadow-inner">
                        <div 
                          className="bg-indigo-500 h-full rounded-full transition-all duration-500"
                          style={{ width: `${progressPct}%` }}
                        />
                      </div>

                      <div className="space-y-2">
                        {roadmap.map(milestone => (
                          <div key={milestone.id} className="flex items-center justify-between p-2.5 rounded-xl border-2 border-black bg-slate-50">
                            <div className="flex items-center gap-2">
                              <button
                                onClick={() => handleToggleMilestone(milestone.id)}
                                className={`w-5 h-5 rounded-md border-2 border-black flex items-center justify-center transition-all ${
                                  milestone.completed ? 'bg-emerald-400' : 'bg-white'
                                }`}
                              >
                                {milestone.completed && <Check size={12} strokeWidth={4}/>}
                              </button>
                              <span className={`text-xs font-bold ${milestone.completed ? 'line-through text-slate-400' : 'text-slate-700'}`}>
                                {milestone.text}
                              </span>
                            </div>
                            <button onClick={() => handleDeleteMilestone(milestone.id)} className="text-slate-400 hover:text-red-500">
                              <Trash2 size={14}/>
                            </button>
                          </div>
                        ))}

                        {totalCount === 0 && (
                          <div className="text-center py-6 border border-dashed border-slate-200 rounded-xl">
                            <p className="text-[11px] font-bold text-slate-400">Chưa có lộ trình cột mốc nào. Hãy thêm một mục tiêu lộ trình của bạn ở dưới!</p>
                          </div>
                        )}
                      </div>

                      <form onSubmit={handleAddMilestone} className="flex gap-2">
                        <input 
                          type="text" 
                          value={newMilestoneText}
                          onChange={e => setNewMilestoneText(e.target.value)}
                          placeholder="Thêm cột mốc lộ trình mới (VD: Hoàn thành giáo trình Minna)..."
                          className="flex-1 font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-1.5 focus:outline-none"
                        />
                        <button type="submit" className="bg-indigo-200 hover:bg-indigo-300 font-black border-2 border-black px-4 rounded-xl text-xs shadow-[2px_2px_0_0_#000]">
                          + Thêm Mốc
                        </button>
                      </form>
                    </section>
                  );
                })()}

              </div>

              {/* Sidebar bên phải của Tab Bản Đồ */}
              <div className="lg:col-span-4 space-y-6">
                
                {/* Bảng Todo-list tương ứng theo Ngày học hiện tại */}
                {(() => {
                  const currCountry = sagaData.find(c => c.id === activeCountryId);
                  const currRegion = currCountry?.regions.find(r => r.id === activeRegionId);
                  const currLevel = currRegion?.levels.find(l => l.id === activeLevelId);
                  if (!currLevel) return null;

                  return (
                    <section className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                      <div>
                        <span className="bg-yellow-100 text-yellow-800 text-[10px] font-black px-2.5 py-0.5 rounded border border-yellow-200">
                          {currLevel.name}
                        </span>
                        <h3 className="text-lg font-black text-slate-900 mt-1">Todo-list & Nhiệm Vụ</h3>
                        <p className="text-[10px] text-slate-400 font-bold">Hãy check hoàn thành để tự động mở khóa chặng tiếp theo và nhận điểm kinh nghiệm!</p>
                      </div>

                      <button 
                        onClick={handleGuiltFreeReschedule}
                        className="w-full bg-orange-100 text-orange-900 hover:bg-orange-200 font-black text-xs py-2 rounded-xl border-2 border-black shadow-[2px_2px_0_0_#000] transition-all"
                      >
                        Gia hạn thảnh thơi (Không áy náy) 💤
                      </button>

                      <form onSubmit={handleAddMapTask} className="flex gap-2">
                        <input 
                          type="text" 
                          value={newTaskText}
                          onChange={e => setNewTaskText(e.target.value)}
                          placeholder="Thêm đầu việc hôm nay..."
                          className="flex-1 font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-2 focus:outline-none"
                        />
                        <button type="submit" className="bg-yellow-300 border-2 border-black hover:bg-yellow-400 font-black px-3 rounded-xl text-xs">
                          Thêm
                        </button>
                      </form>

                      <div className="space-y-2 max-h-48 overflow-y-auto pr-1">
                        {(currLevel.tasks || []).map(task => (
                          <div 
                            key={task.id}
                            className={`flex items-center justify-between p-2.5 rounded-xl border-2 transition-all ${
                              task.completed 
                              ? 'bg-slate-50 border-slate-200 opacity-60' 
                              : 'bg-white border-black shadow-[2px_2px_0_0_#000] hover:-translate-y-0.5'
                            }`}
                          >
                            <div className="flex items-center gap-2">
                              <button 
                                onClick={() => handleToggleMapTask(task.id)}
                                className={`w-6 h-6 rounded-lg border-2 flex items-center justify-center transition-all ${
                                  task.completed 
                                  ? 'bg-emerald-400 border-emerald-400 text-white' 
                                  : 'border-black bg-white hover:bg-slate-100'
                                }`}
                              >
                                {task.completed && <Check size={14} strokeWidth={4} />}
                              </button>
                              <span className={`font-bold text-xs ${task.completed ? 'line-through text-slate-400' : 'text-slate-800'}`}>
                                {task.text}
                              </span>
                            </div>
                            <button 
                              onClick={() => handleDeleteMapTask(task.id)}
                              className="text-slate-400 hover:text-red-500"
                            >
                              <Trash2 size={14} />
                            </button>
                          </div>
                        ))}

                        {(currLevel.tasks || []).length === 0 && (
                          <div className="text-center py-6 border-2 border-dashed border-slate-200 rounded-xl">
                            <p className="text-[11px] font-bold text-slate-400">Trống trơn. Nhập mục tiêu ngày thôi!</p>
                          </div>
                        )}
                      </div>

                      {/* KHU VỰC GẮN TÀI LIỆU HỌC TẬP (LINKS & FILES) CHO NGÀY NÀY */}
                      <div className="border-t border-slate-100 pt-3 space-y-3">
                        <h4 className="text-xs font-black text-slate-700 flex items-center gap-1">
                          <LinkIcon size={14}/> Tài Liệu & File Cần Học
                        </h4>

                        {/* Danh sách link và file */}
                        <div className="space-y-1.5 max-h-32 overflow-y-auto">
                          {(currLevel.links || []).map((link, idx) => (
                            <div key={idx} className="flex justify-between items-center bg-sky-50 p-2 rounded-xl border border-sky-200 text-xs">
                              <a href={link.url} target="_blank" rel="noopener noreferrer" className="font-bold text-sky-800 hover:underline flex items-center gap-1.5 truncate max-w-[180px]">
                                <ExternalLink size={12}/> {link.name}
                              </a>
                              <button onClick={() => handleDeleteStudyLink(idx)} className="text-slate-400 hover:text-red-500">
                                <Trash2 size={12}/>
                              </button>
                            </div>
                          ))}

                          {(currLevel.files || []).map((file, idx) => (
                            <div key={idx} className="flex justify-between items-center bg-emerald-50 p-2 rounded-xl border border-emerald-200 text-xs">
                              <span className="font-bold text-emerald-800 flex items-center gap-1.5 truncate max-w-[180px]">
                                <FileText size={12}/> {file.name} ({file.size})
                              </span>
                              <button onClick={() => handleDeleteStudyFile(idx)} className="text-slate-400 hover:text-red-500">
                                <Trash2 size={12}/>
                              </button>
                            </div>
                          ))}
                        </div>

                        {/* Form thêm tài liệu link */}
                        <form onSubmit={handleAddStudyLink} className="space-y-1">
                          <div className="flex gap-1.5">
                            <input 
                              type="text"
                              placeholder="Tên bài giảng/video..."
                              value={newLinkName}
                              onChange={e => setNewLinkName(e.target.value)}
                              className="flex-1 text-[10px] font-bold bg-slate-50 border border-slate-300 rounded-lg px-2 py-1 focus:outline-none"
                            />
                            <input 
                              type="text"
                              placeholder="Dán link (http)..."
                              value={newLinkUrl}
                              onChange={e => setNewLinkUrl(e.target.value)}
                              className="flex-1 text-[10px] font-bold bg-slate-50 border border-slate-300 rounded-lg px-2 py-1 focus:outline-none"
                            />
                            <button type="submit" className="bg-sky-200 hover:bg-sky-300 px-2 py-1 rounded-lg text-[10px] font-black border border-sky-400">
                              Ghim Link
                            </button>
                          </div>
                        </form>

                        {/* Tải tệp tin đính kèm */}
                        <div className="flex items-center gap-2">
                          <button
                            type="button"
                            onClick={() => fileInputRefDay.current?.click()}
                            className="w-full bg-slate-100 hover:bg-slate-200 border border-slate-300 text-[10px] font-black py-1.5 rounded-xl flex items-center justify-center gap-1.5 transition-all shadow-sm"
                          >
                            <FileUp size={12}/> Tải File Học Lên Mốc Này
                          </button>
                          <input 
                            type="file"
                            ref={fileInputRefDay}
                            onChange={handleStudyFileUpload}
                            className="hidden"
                          />
                        </div>
                      </div>

                    </section>
                  );
                })()}

                {/* SNOOPY AI MENTOR & COACH BUBBLE (ADHD ASSISTANT) */}
                <section className="bg-amber-100 p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-3 relative overflow-hidden">
                  <div className="absolute top-2 right-4 text-xl">🦴</div>
                  <h3 className="font-black text-xs md:text-sm text-slate-800 flex items-center gap-1">
                    <MessageSquare size={16} className="text-amber-600 animate-pulse"/> SNOOPY AI MENTOR
                  </h3>

                  <div className="bg-white p-3 rounded-2xl border-2 border-black text-xs font-bold text-slate-700 leading-relaxed min-h-[80px]">
                    {isAiLoading ? (
                      <span className="flex items-center gap-1.5 text-slate-400 font-bold"><RefreshCw size={14} className="animate-spin" /> Snoopy AI đang phân tích dữ liệu...</span>
                    ) : (
                      aiChatHistory[aiChatHistory.length - 1]?.text || "Gâu gâu! Mình sẵn sàng hỗ trợ bạn bất cứ lúc nào!"
                    )}
                  </div>

                  {/* AI Quick Prompt Actions */}
                  <div className="grid grid-cols-2 gap-1.5">
                    <button
                      onClick={async () => {
                        setIsAiLoading(true);
                        playAudioFeedback('click', isMuted);
                        const prompt = `Phân tích tiến trình học kỹ năng hiện tại: ${(sagaData.find(c => c.id === activeCountryId)?.regions?.find(r => r.id === activeRegionId)?.name || 'Chưa chọn')}. Hiện đang ở Level ${(sagaData.find(c => c.id === activeCountryId)?.regions?.find(r => r.id === activeRegionId)?.level || 1)}, XP hiện tại là ${(sagaData.find(c => c.id === activeCountryId)?.regions?.find(r => r.id === activeRegionId)?.xp || 0)}/1000. Hãy đưa ra 1 lời khuyên thảnh thơi truyền động lực để tối ưu năng lượng học, viết siêu ngắn gọn trong 2 câu nhé!`;
                        const res = await callGeminiAPI(prompt, "Bạn là Snoopy AI Coach khích lệ người học ADHD.");
                        if (res) {
                          setAiChatHistory(prev => [...prev, { role: 'user', text: 'Snoopy phân tích tiến độ giúp mình.' }, { role: 'model', text: res }]);
                          triggerDopamine("🐕 Phân tích học tập thành công!", 3);
                        } else {
                          setAiChatHistory(prev => [...prev, { role: 'model', text: 'Gâu! Đang nghẽn kết nối, hãy thử lại sau nha bạn thân!' }]);
                        }
                        setIsAiLoading(false);
                      }}
                      className="bg-slate-950 hover:bg-slate-800 text-white text-[9px] font-black py-1.5 rounded-lg border border-black"
                    >
                      Phân Tích Tiến Độ 📈
                    </button>
                    <button
                      onClick={async () => {
                        setIsAiLoading(true);
                        playAudioFeedback('click', isMuted);
                        const prompt = "Hãy viết một câu danh ngôn hay, ngắn gọn, truyền cảm hứng đặc biệt cho học sinh ADHD bớt xao nhãng và tự hào về bản thân. Viết siêu ngắn trong 1 câu nhé!";
                        const res = await callGeminiAPI(prompt, "Bạn là Snoopy AI khích lệ động lực.");
                        if (res) {
                          setAiChatHistory(prev => [...prev, { role: 'user', text: 'Hãy động viên mình.' }, { role: 'model', text: res }]);
                          triggerDopamine("🌟 Nhận năng lượng vũ trụ thành công!", 4);
                        }
                        setIsAiLoading(false);
                      }}
                      className="bg-yellow-300 hover:bg-yellow-400 text-slate-900 text-[9px] font-black py-1.5 rounded-lg border border-black"
                    >
                      Động Viên Mình Đi! 🦴
                    </button>
                  </div>
                </section>

                {/* SMART STUDY PLANNER & TIMETABLE (CHỐNG BURNOUT) */}
                <section className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                  <div className="flex justify-between items-center border-b border-slate-100 pb-2">
                    <h3 className="font-black text-sm text-slate-900 flex items-center gap-1.5">
                      <Calendar className="text-amber-500 animate-bounce" size={18}/> SMART STUDY PLANNER
                    </h3>
                  </div>

                  <div className="bg-slate-50 p-3 rounded-2xl border border-slate-200 text-xs space-y-2.5">
                    <div>
                      <label className="block text-[9px] font-black text-slate-400">Thời gian rảnh của bạn trong ngày:</label>
                      <input 
                        type="text"
                        value={plannerFreeHours}
                        onChange={e => setPlannerFreeHours(e.target.value)}
                        placeholder="VD: 3 tiếng buổi tối, rảnh chiều..."
                        className="w-full bg-white border border-slate-300 rounded-lg px-2.5 py-1 font-black text-slate-700 focus:outline-none"
                      />
                    </div>

                    <div className="grid grid-cols-2 gap-2">
                      <div>
                        <label className="block text-[9px] font-black text-slate-400">Độ gấp gáp/Deadline:</label>
                        <input 
                          type="text"
                          value={plannerDeadline}
                          onChange={e => setPlannerDeadline(e.target.value)}
                          placeholder="VD: 1 tháng nữa thi..."
                          className="w-full bg-white border border-slate-300 rounded-lg px-2 py-1 font-black text-slate-700 focus:outline-none"
                        />
                      </div>
                      <div>
                        <label className="block text-[9px] font-black text-slate-400">Độ ưu tiên:</label>
                        <select
                          value={plannerPriority}
                          onChange={e => setPlannerPriority(e.target.value)}
                          className="w-full bg-white border border-slate-300 rounded-lg px-2 py-1 font-black text-slate-700 focus:outline-none"
                        >
                          <option value="Bình thường ☕">Bình thường ☕</option>
                          <option value="Cao ⚡">Cao ⚡</option>
                          <option value="Rất Cao 🔥">Rất Cao 🔥</option>
                        </select>
                      </div>
                    </div>

                    <button
                      onClick={handleAiPlanSchedule}
                      disabled={isPlannerLoading}
                      className="w-full bg-yellow-300 hover:bg-yellow-400 border border-black font-black text-[10px] py-1.5 rounded-lg text-slate-900 transition-all shadow-sm"
                    >
                      {isPlannerLoading ? 'ĐANG TÍNH TOÁN LỊCH HỌC...' : 'AI Lên Lịch Tối Ưu Chống Burnout 📅'}
                    </button>
                  </div>

                  {/* Hiển thị thời khóa biểu tối ưu đề xuất */}
                  <div className="space-y-1.5">
                    <span className="text-[10px] font-black text-slate-400 uppercase tracking-wider block">Thời khóa biểu tối ưu hôm nay</span>
                    <div className="space-y-1.5 max-h-48 overflow-y-auto pr-1">
                      {plannerSuggestedSchedule.map((block, idx) => (
                        <div key={idx} className="bg-white p-2.5 rounded-xl border-2 border-black flex items-center justify-between gap-1.5 hover:scale-[1.01] transition-transform">
                          <div className="flex flex-col gap-0.5 max-w-[70%]">
                            <span className="text-[10px] font-black text-indigo-600 block">{block.time}</span>
                            <span className="text-xs font-bold text-slate-800 leading-snug">{block.activity}</span>
                          </div>
                          <div className="bg-orange-100 text-orange-900 border border-orange-200 text-[8px] font-black px-2 py-0.5 rounded-full shrink-0">
                            Nghỉ {block.break}
                          </div>
                        </div>
                      ))}
                    </div>
                  </div>
                </section>

                {/* Đồng hồ Pomodoro tập trung */}
                <section className="bg-gradient-to-br from-rose-500 to-pink-600 text-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] relative overflow-hidden">
                  <div className="absolute top-2 right-6 text-xl animate-bounce">✨</div>

                  <div className="flex justify-between items-center mb-4">
                    <div className="flex bg-white/20 rounded-full border-2 border-white p-0.5">
                      <button 
                        onClick={() => { setTimerMode('focus'); setTimeLeft(25 * 60); setIsActive(false); playAudioFeedback('click', isMuted); }}
                        className={`px-3 py-1 rounded-full font-black text-[10px] transition-all ${timerMode === 'focus' ? 'bg-white text-rose-600' : 'text-white'}`}
                      >
                        Học Tập 🎯
                      </button>
                      <button 
                        onClick={() => { setTimerMode('break'); setTimeLeft(5 * 60); setIsActive(false); playAudioFeedback('click', isMuted); }}
                        className={`px-3 py-1 rounded-full font-black text-[10px] transition-all ${timerMode === 'break' ? 'bg-white text-rose-600' : 'text-white'}`}
                      >
                        Giải Lao ☕
                      </button>
                    </div>
                  </div>

                  <div className="flex flex-col items-center justify-center">
                    <div className="text-4xl font-black tracking-tighter mb-4 bg-white text-slate-900 px-6 py-2 rounded-xl border-2 border-black">
                      {Math.floor(timeLeft / 60).toString().padStart(2, '0')}:{(timeLeft % 60).toString().padStart(2, '0')}
                    </div>

                    <div className="flex gap-2">
                      <button 
                        onClick={() => { toggleTimer(); playAudioFeedback('click', isMuted); }}
                        className={`flex items-center gap-1 px-4 py-2 rounded-lg font-black text-xs border-2 border-black transition-all shadow-[2px_2px_0_0_#000] ${isActive ? 'bg-red-300 text-slate-900' : 'bg-yellow-300 text-slate-900'}`}
                      >
                        {isActive ? <Pause size={12} strokeWidth={3} /> : <Play size={12} strokeWidth={3} />}
                        {isActive ? 'Tạm dừng' : 'Bắt đầu'}
                      </button>
                      <button 
                        onClick={() => { resetTimer(); playAudioFeedback('error', isMuted); }}
                        className="p-2 rounded-lg bg-white text-black border-2 border-black hover:bg-slate-100 transition-all shadow-[2px_2px_0_0_#000]"
                      >
                        <RotateCcw size={14} strokeWidth={3} />
                      </button>
                    </div>
                  </div>
                </section>

                {/* Biểu đồ tập trung hàng tuần */}
                <section className="bg-white p-6 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                  <div className="flex justify-between items-center border-b-2 border-dashed border-slate-100 pb-3">
                    <div className="flex items-center gap-2">
                      <BarChart2 className="text-indigo-500 animate-pulse" size={20}/>
                      <h3 className="font-black text-sm text-slate-900">Biểu Đồ Tập Trung</h3>
                    </div>
                  </div>

                  <div className="bg-slate-50 border-2 border-black rounded-2xl p-4 h-48 flex items-end justify-between gap-2 relative">
                    {weeklyData.map((data, idx) => {
                      const maxVal = 150;
                      const barPercent = Math.min((data.val / maxVal) * 100, 100);
                      
                      return (
                        <div key={idx} className="flex-1 flex flex-col items-center h-full justify-end group cursor-pointer relative">
                          <div className="absolute bottom-full mb-1 bg-slate-900 text-white text-[9px] px-1.5 py-0.5 rounded opacity-0 group-hover:opacity-100 transition-opacity font-bold pointer-events-none whitespace-nowrap z-20">
                            {data.val} phút
                          </div>

                          <div 
                            className={`w-full rounded-t-lg border-2 border-black transition-all duration-500 relative ${data.val > 0 ? 'bg-indigo-300 shadow-[2px_2px_0_0_#000]' : 'bg-slate-200 border-dashed'}`}
                            style={{ height: `${Math.max(barPercent, 6)}%` }}
                          >
                            {data.val > 45 && (
                              <div className="absolute inset-x-0 bottom-2 text-center text-[10px] opacity-40">🐾</div>
                            )}
                          </div>

                          <span className="text-[10px] font-black text-slate-600 mt-2">{data.day}</span>
                        </div>
                      );
                    })}
                  </div>
                </section>

              </div>
            </div>
          )}

          {/* Tab Ghi Chú - TAKE NOTE (Phân chia theo Kỹ năng & Ngày học để tránh dồn ứ) */}
          {activeTab === 'notes' && (
            <div className="space-y-6">
              {(() => {
                const currentCountry = sagaData.find(c => c.id === activeCountryId);
                const currentRegion = currentCountry?.regions.find(r => r.id === activeRegionId);
                
                return (
                  <div className="bg-orange-50 border-4 border-black p-5 rounded-[2.5rem] flex flex-col md:flex-row justify-between items-center gap-4">
                    <div>
                      <h2 className="text-xl font-black text-slate-900 flex items-center gap-1.5">
                        <FileText className="text-orange-500" /> Sổ Tay Ghi Chú Theo Môn Học: {currentRegion ? currentRegion.name : 'Chưa chọn'}
                      </h2>
                      <p className="text-xs font-bold text-slate-500">
                        * Ghi chú này chỉ lọc hiển thị riêng cho môn học và kỹ năng đang được lựa chọn ở Bản Đồ Lộ Trình!
                      </p>
                    </div>

                    <div className="flex items-center gap-2 shrink-0">
                      <span className="text-xs font-black text-slate-600">Đổi Học Phần:</span>
                      <select
                        value={activeRegionId}
                        onChange={(e) => {
                          setActiveRegionId(e.target.value);
                          playAudioFeedback('click', isMuted);
                        }}
                        className="bg-white border-2 border-black px-3 py-1.5 rounded-xl font-black text-xs text-slate-800 focus:outline-none shadow-[2px_2px_0_0_#000]"
                      >
                        {currentCountry?.regions.map(r => (
                          <option key={r.id} value={r.id}>{r.name}</option>
                        ))}
                      </select>
                    </div>
                  </div>
                );
              })()}

              <div className="grid grid-cols-1 lg:grid-cols-12 gap-6">
                <div className="lg:col-span-4">
                  <section className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                    <h3 className="font-black text-sm flex items-center gap-1.5 text-slate-900">
                      <PlusCircle className="text-orange-500" /> Viết Ghi Chú Mới
                    </h3>

                    <form onSubmit={handleAddNote} className="space-y-3">
                      <div>
                        <label className="block text-[10px] font-black text-slate-500 mb-0.5">Tiêu đề ghi chú</label>
                        <input 
                          type="text" 
                          value={newNoteTitle}
                          onChange={e => setNewNoteTitle(e.target.value)}
                          placeholder="Nhập tiêu đề (VD: Công thức nhớ từ)..."
                          className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-2 focus:outline-none"
                        />
                      </div>

                      <div>
                        <label className="block text-[10px] font-black text-slate-500 mb-0.5">Nội dung chi tiết</label>
                        <textarea 
                          rows="4"
                          value={newNoteContent}
                          onChange={e => setNewNoteContent(e.target.value)}
                          placeholder="Nội dung ghi nhớ..."
                          className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl p-3 focus:outline-none resize-none"
                        />
                      </div>

                      <div>
                        <label className="block text-[10px] font-black text-slate-500 mb-1">Màu giấy Note</label>
                        <div className="flex gap-2">
                          {[
                            { color: 'bg-yellow-100', name: 'Vàng' },
                            { color: 'bg-blue-100', name: 'Xanh' },
                            { color: 'bg-pink-100', name: 'Hồng' },
                            { color: 'bg-emerald-100', name: 'Xanh Lá' },
                            { color: 'bg-purple-100', name: 'Tím' }
                          ].map(opt => (
                            <button
                              key={opt.color}
                              type="button"
                              onClick={() => setNewNoteColor(opt.color)}
                              className={`w-7 h-7 rounded-full border-2 border-black ${opt.color} transition-all ${newNoteColor === opt.color ? 'scale-120 border-3 ring-2 ring-slate-400' : ''}`}
                              title={opt.name}
                            />
                          ))}
                        </div>
                      </div>

                      <button 
                        type="submit"
                        className="w-full bg-yellow-300 hover:bg-yellow-400 text-slate-900 border-2 border-black font-black py-2.5 rounded-xl text-xs shadow-[2px_2px_0_0_#000] transition-all"
                      >
                        Ghim Lên Bảng 📌
                      </button>
                    </form>
                  </section>
                </div>

                <div className="lg:col-span-8">
                  <section className="bg-slate-100 p-6 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] min-h-[350px]">
                    <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                      {(notesByRegion[activeRegionId] || []).map(note => (
                        <div 
                          key={note.id}
                          className={`p-5 rounded-3xl border-3 border-black shadow-[3px_3px_0_0_#000] ${note.color} relative transform rotate-1 hover:rotate-0 transition-all flex flex-col justify-between min-h-[140px]`}
                        >
                          <button 
                            onClick={() => handleDeleteNote(note.id)}
                            className="absolute top-2.5 right-2.5 text-slate-500 hover:text-red-500 transition-colors"
                          >
                            <Trash2 size={16} />
                          </button>

                          <div>
                            <span className="text-[9px] font-bold text-slate-400 block mb-1">{note.date}</span>
                            <h4 className="font-black text-sm text-slate-900 mb-1.5 leading-snug">{note.title}</h4>
                            <p className="text-xs font-semibold text-slate-700 leading-relaxed whitespace-pre-wrap">{note.content}</p>
                          </div>
                        </div>
                      ))}

                      {(!notesByRegion[activeRegionId] || notesByRegion[activeRegionId].length === 0) && (
                        <div className="col-span-2 text-center py-20 border-4 border-dashed border-slate-300 rounded-3xl bg-white/40">
                          <Smile size={36} className="mx-auto text-slate-400 mb-2" />
                          <p className="font-black text-sm text-slate-500">Học phần này chưa có ghi chú nào. Hãy tự viết ghi chú đầu tiên của bạn ở form bên trái nhé! 🐾</p>
                        </div>
                      )}
                    </div>
                  </section>
                </div>
              </div>
            </div>
          )}

          {/* Tab Đấu Trường Ôn Tập (Phân tách theo môn học) */}
          {activeTab === 'review' && (
            <div className="space-y-6">
              {(() => {
                const currentCountry = sagaData.find(c => c.id === activeCountryId);
                const currentRegion = currentCountry?.regions.find(r => r.id === activeRegionId);
                
                return (
                  <div className="bg-pink-50 border-4 border-black p-5 rounded-[2.5rem] flex flex-col md:flex-row justify-between items-center gap-4">
                    <div>
                      <h2 className="text-xl font-black text-slate-900 flex items-center gap-1.5">
                        <Trophy className="text-pink-500 animate-bounce" /> Đấu Trường Ôn Tập: {currentRegion ? currentRegion.name : 'Chưa chọn'}
                      </h2>
                      <p className="text-xs font-bold text-slate-500">
                        * Bộ câu hỏi ôn tập chỉ hiển thị rạch ròi theo Học phần được lựa chọn!
                      </p>
                    </div>

                    <div className="flex items-center gap-2 shrink-0">
                      <span className="text-xs font-black text-slate-600">Đổi Học Phần:</span>
                      <select
                        value={activeRegionId}
                        onChange={(e) => {
                          setActiveRegionId(e.target.value);
                          playAudioFeedback('click', isMuted);
                        }}
                        className="bg-white border-2 border-black px-3 py-1.5 rounded-xl font-black text-xs text-slate-800 focus:outline-none shadow-[2px_2px_0_0_#000]"
                      >
                        {currentCountry?.regions.map(r => (
                          <option key={r.id} value={r.id}>{r.name}</option>
                        ))}
                      </select>
                    </div>
                  </div>
                );
              })()}

              <div className="grid grid-cols-1 lg:grid-cols-12 gap-6">
                
                <div className="lg:col-span-8 space-y-4">
                  
                  <div className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                    <div className="flex flex-wrap bg-slate-100 p-1 rounded-2xl gap-1 border-2 border-black">
                      {[
                        { id: 'match', name: 'Nối Cặp 🧩' },
                        { id: 'flip', name: 'Lật Thẻ 🃏' },
                        { id: 'quiz', name: 'Trắc Nghiệm 🎯' },
                        { id: 'type', name: 'Gõ Phím ⌨️' }
                      ].map(mode => (
                        <button
                          key={mode.id}
                          onClick={() => { setReviewMode(mode.id); resetMatchGame(); playAudioFeedback('click', isMuted); }}
                          className={`font-black px-3.5 py-1.5 rounded-xl text-xs transition-all flex-1 ${reviewMode === mode.id ? 'bg-slate-900 text-white' : 'text-slate-800 hover:bg-slate-200'}`}
                        >
                          {mode.name}
                        </button>
                      ))}
                    </div>

                    {/* CHẾ ĐỘ 1: NỐI CẶP TRỰC QUAN (MATCHING) */}
                    {reviewMode === 'match' && (
                      <div className="space-y-4">
                        <div className="bg-sky-50 p-2.5 rounded-xl border border-black text-center font-black text-xs text-indigo-900">
                          {matchGameStatus}
                        </div>

                        {(matchingTermsByRegion[activeRegionId] || []).length > 0 ? (
                          <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div className="space-y-2">
                              <span className="block text-center font-black text-xs bg-indigo-100 border-2 border-black py-1 rounded-lg">THUẬT NGỮ</span>
                              {(matchingTermsByRegion[activeRegionId] || []).map(term => {
                                const isMatched = matchedPairs.includes(term.matchId);
                                const isSelected = selectedTerm?.id === term.id;
                                return (
                                  <button
                                    key={term.id}
                                    onClick={() => handleTermSelect(term)}
                                    disabled={isMatched}
                                    className={`w-full text-left p-3 rounded-xl border-2 font-black text-xs transition-all ${
                                      isMatched 
                                      ? 'bg-emerald-100 border-emerald-200 text-emerald-600 opacity-50 line-through' 
                                      : isSelected 
                                      ? 'bg-yellow-200 border-black shadow-[2px_2px_0_0_#000]' 
                                      : 'bg-white border-slate-300 hover:border-black'
                                    }`}
                                  >
                                    {term.text}
                                  </button>
                                );
                              })}
                            </div>

                            <div className="space-y-2">
                              <span className="block text-center font-black text-xs bg-pink-100 border-2 border-black py-1 rounded-lg">ĐỊNH NGHĨA</span>
                              {(matchingDefsByRegion[activeRegionId] || []).map(def => {
                                const isMatched = matchedPairs.includes(def.matchId);
                                const isSelected = selectedDef?.id === def.id;
                                return (
                                  <button
                                    key={def.id}
                                    onClick={() => handleDefSelect(def)}
                                    disabled={isMatched}
                                    className={`w-full text-left p-3 rounded-xl border-2 font-black text-xs transition-all ${
                                      isMatched 
                                      ? 'bg-emerald-100 border-emerald-200 text-emerald-600 opacity-50 line-through' 
                                      : isSelected 
                                      ? 'bg-yellow-200 border-black shadow-[2px_2px_0_0_#000]' 
                                      : 'bg-white border-slate-300 hover:border-black'
                                    }`}
                                  >
                                    {def.text}
                                  </button>
                                );
                              })}
                            </div>
                          </div>
                        ) : (
                          <div className="text-center py-10 border-2 border-dashed border-slate-200 rounded-3xl">
                            <p className="font-bold text-xs text-slate-400">Không có câu hỏi nối cặp nào được lưu trữ ở học phần này.</p>
                          </div>
                        )}
                      </div>
                    )}

                    {/* CHẾ ĐỘ 2: LẬT THẺ THÔNG MINH */}
                    {reviewMode === 'flip' && (
                      <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                        {(flashcardsByRegion[activeRegionId] || []).map(card => (
                          <div key={card.id} className="bg-white p-4 rounded-3xl border-4 border-black shadow-[4px_4px_0_0_#000] relative">
                            <button 
                              onClick={() => {
                                const currentCards = flashcardsByRegion[activeRegionId] || [];
                                setFlashcardsByRegion({
                                  ...flashcardsByRegion,
                                  [activeRegionId]: currentCards.filter(c => c.id !== card.id)
                                });
                              }} 
                              className="absolute top-2 right-2 text-slate-400 hover:text-red-500"
                            >
                              <Trash2 size={14} />
                            </button>
                            <div className="border-b border-dashed border-slate-100 pb-2 mb-2 pr-4">
                              <span className="bg-pink-100 text-pink-700 text-[9px] px-2 py-0.5 rounded border border-pink-200 font-black">LẬT THẺ THÔNG MINH</span>
                              <h4 className="font-black text-xs text-slate-800 mt-2 leading-snug">{card.q}</h4>
                            </div>
                            <div 
                              onClick={() => {
                                const currentCards = flashcardsByRegion[activeRegionId] || [];
                                setFlashcardsByRegion({
                                  ...flashcardsByRegion,
                                  [activeRegionId]: currentCards.map(c => c.id === card.id ? { ...c, flipped: !c.flipped } : c)
                                });
                                playAudioFeedback('click', isMuted);
                              }}
                              className={`min-h-[80px] rounded-2xl border-2 border-black cursor-pointer flex items-center justify-center p-2 transition-all ${card.flipped ? 'bg-[#A7F3D0]' : 'bg-slate-50'}`}
                            >
                              <p className="font-black text-xs text-center text-slate-800">
                                {card.flipped ? card.a : 'Bấm để lật thẻ 🐾'}
                              </p>
                            </div>
                          </div>
                        ))}
                        {(!flashcardsByRegion[activeRegionId] || flashcardsByRegion[activeRegionId].length === 0) && (
                          <div className="col-span-2 text-center py-10 border-2 border-dashed border-slate-200 rounded-3xl">
                            <p className="font-bold text-xs text-slate-400">Không có thẻ flashcard nào được tìm thấy ở học phần này.</p>
                          </div>
                        )}
                      </div>
                    )}

                    {/* CHẾ ĐỘ 3: TRẮC NGHIỆM TƯƠNG TÁC */}
                    {reviewMode === 'quiz' && (
                      <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                        {(flashcardsByRegion[activeRegionId] || []).map(card => (
                          <div key={card.id} className="bg-white p-4 rounded-3xl border-4 border-black shadow-[4px_4px_0_0_#000] relative">
                            <div className="mb-2">
                              <span className="bg-yellow-100 text-yellow-800 text-[9px] px-2 py-0.5 rounded font-black">CÂU HỎI NHIỀU LỰA CHỌN</span>
                              <h4 className="font-black text-xs text-slate-800 mt-1">{card.q}</h4>
                            </div>
                            <div className="space-y-1">
                              {card.options.map((opt, i) => (
                                <button 
                                  key={i}
                                  onClick={() => {
                                    if (opt === card.a) {
                                      triggerDopamine("Tuyệt hảo! Đáp án hoàn toàn chính xác! 🧠🔥", 3);
                                      gainXP(15);
                                    } else {
                                      playAudioFeedback('error', isMuted);
                                    }
                                  }}
                                  className="w-full text-left font-bold text-[11px] p-2 rounded-lg border border-slate-200 hover:border-black transition-all flex items-center gap-1.5"
                                >
                                  <span className="w-5 h-5 bg-slate-100 rounded-full border border-black flex items-center justify-center font-black text-[9px] shrink-0">{String.fromCharCode(65 + i)}</span>
                                  <span className="truncate">{opt}</span>
                                </button>
                              ))}
                            </div>
                          </div>
                        ))}
                      </div>
                    )}

                    {/* CHẾ ĐỘ 4: GÕ PHÍM TRẢ LỜI NGẮN */}
                    {reviewMode === 'type' && (
                      <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                        {(flashcardsByRegion[activeRegionId] || []).map(card => (
                          <div key={card.id} className="bg-white p-4 rounded-3xl border-4 border-black shadow-[4px_4px_0_0_#000] relative">
                            <div className="mb-2">
                              <span className="bg-purple-100 text-purple-800 text-[9px] px-2 py-0.5 rounded font-black">TỰ LUẬN TRẢ LỜI NGẮN</span>
                              <h4 className="font-black text-xs text-slate-800 mt-1">{card.q}</h4>
                            </div>
                            <div className="space-y-2">
                              <div className="flex gap-2">
                                <input 
                                  type="text" 
                                  placeholder="Gõ câu trả lời chuẩn xác..."
                                  value={typeInputs[card.id] || ''}
                                  onChange={e => setTypeInputs({...typeInputs, [card.id]: e.target.value})}
                                  className="flex-1 font-bold text-xs bg-slate-50 border-2 border-black rounded-lg px-2 py-1.5 focus:outline-none"
                                />
                                <button 
                                  onClick={() => {
                                    const userAns = typeInputs[card.id] || '';
                                    if (userAns.toLowerCase().trim() === card.a.toLowerCase().trim()) {
                                      triggerDopamine("Nhập chính xác từng kí tự! Quá đỉnh! ⌨️🎉", 3);
                                      gainXP(25);
                                    } else {
                                      playAudioFeedback('error', isMuted);
                                    }
                                  }}
                                  className="bg-slate-900 text-white font-black text-xs px-3 rounded-lg hover:bg-slate-800"
                                >
                                  Gửi
                                </button>
                              </div>
                            </div>
                          </div>
                        ))}
                      </div>
                    )}

                  </div>

                </div>

                {/* Thanh biên tập học tập bên phải của Tab Ôn Tập */}
                <div className="lg:col-span-4 space-y-6">
                  
                  <section className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-3">
                    <h3 className="font-black text-sm flex items-center gap-1.5">
                      <PlusCircle className="text-pink-500" size={16} /> Tự Tạo Flashcard Học Tập
                    </h3>
                    
                    <form onSubmit={handleCreateCustomFlashcard} className="space-y-2">
                      <div>
                        <label className="block text-[10px] font-black text-slate-500 mb-0.5">Câu hỏi mặt trước</label>
                        <input 
                          type="text"
                          value={newCardQ}
                          onChange={e => setNewCardQ(e.target.value)}
                          placeholder="Ví dụ: Thủ đô của Nhật Bản là gì?"
                          className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-2 py-1.5 focus:outline-none"
                        />
                      </div>

                      <div>
                        <label className="block text-[10px] font-black text-slate-500 mb-0.5">Mặt sau (Đáp án chuẩn)</label>
                        <input 
                          type="text"
                          value={newCardA}
                          onChange={e => setNewCardA(e.target.value)}
                          placeholder="Ví dụ: Tokyo"
                          className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-2 py-1.5 focus:outline-none"
                        />
                      </div>

                      <div className="bg-slate-50 p-2 rounded-lg border border-slate-200">
                        <label className="block text-[9px] font-black text-slate-400 mb-1 uppercase">Các đáp án gây nhiễu</label>
                        <div className="space-y-1">
                          <input type="text" placeholder="Nhiễu 1..." value={newCardOpt2} onChange={e => setNewCardOpt2(e.target.value)} className="w-full font-semibold text-[10px] px-2 py-1 border rounded" />
                          <input type="text" placeholder="Nhiễu 2..." value={newCardOpt3} onChange={e => setNewCardOpt3(e.target.value)} className="w-full font-semibold text-[10px] px-2 py-1 border rounded" />
                          <input type="text" placeholder="Nhiễu 3..." value={newCardOpt4} onChange={e => setNewCardOpt4(e.target.value)} className="w-full font-semibold text-[10px] px-2 py-1 border rounded" />
                        </div>
                      </div>

                      <button type="submit" className="w-full bg-[#FBCFE8] hover:bg-pink-300 border-2 border-black font-black py-2 rounded-xl text-xs shadow-[2px_2px_0_0_#000]">
                        Lưu thẻ ôn tập 🃏
                      </button>
                    </form>
                  </section>

                  <section className="bg-white p-5 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-3">
                    <h3 className="font-black text-sm flex items-center gap-1.5">
                      <PlusCircle className="text-indigo-500" size={16} /> Thêm Cặp Nối Từ Khóa
                    </h3>
                    <form onSubmit={handleAddManualTerm} className="space-y-2">
                      <input 
                        type="text"
                        placeholder="Thuật ngữ bên trái (VD: Sun)..."
                        value={newTermText}
                        onChange={e => setNewTermText(e.target.value)}
                        className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-2 py-1.5 focus:outline-none"
                      />
                      <input 
                        type="text"
                        placeholder="Định nghĩa bên phải (VD: Mặt trời)..."
                        value={newDefText}
                        onChange={e => setNewDefText(e.target.value)}
                        className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-2 py-1.5 focus:outline-none"
                      />
                      <button type="submit" className="w-full bg-indigo-200 hover:bg-indigo-300 font-black py-2 rounded-xl text-xs border-2 border-black">
                        Lưu cặp từ nối 🧩
                      </button>
                    </form>
                  </section>

                </div>

              </div>
            </div>
          )}

          {/* Tab Sức Khỏe & Thể Chất (Có tính lượng nước giảm cân & Sân tập Gym) */}
          {activeTab === 'health' && (
            <div className="space-y-6">
              <div className="grid grid-cols-1 lg:grid-cols-12 gap-6">
                
                <div className="lg:col-span-7">
                  <section className="bg-gradient-to-br from-emerald-600 to-teal-800 text-white p-6 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-5 relative overflow-hidden">
                    <div className="absolute -right-6 -top-6 w-32 h-32 bg-teal-500/20 rounded-full pointer-events-none"></div>

                    <div className="flex items-center gap-3 border-b border-white/20 pb-3">
                      <div className="w-12 h-12 bg-white/20 border-2 border-white rounded-xl flex items-center justify-center text-2xl">🥑</div>
                      <div>
                        <h2 className="text-xl font-black text-white">Chỉ Số BMI & Sức Khỏe Cho ADHD</h2>
                        <p className="text-xs text-emerald-100">Tính toán nước nạp vào cơ thể hỗ trợ giảm cân lành mạnh</p>
                      </div>
                    </div>

                    <div className="grid grid-cols-3 gap-3 text-slate-800">
                      <div className="bg-white p-3 rounded-2xl border-2 border-black">
                        <label className="block text-[9px] font-black text-slate-500 mb-1">Chiều cao (cm)</label>
                        <input 
                          type="number" 
                          value={height}
                          onChange={e => setHeight(e.target.value)}
                          className="w-full font-black text-sm bg-transparent focus:outline-none"
                        />
                      </div>
                      <div className="bg-white p-3 rounded-2xl border-2 border-black">
                        <label className="block text-[9px] font-black text-slate-500 mb-1">Cân nặng (kg)</label>
                        <input 
                          type="number" 
                          value={weight}
                          onChange={e => setWeight(e.target.value)}
                          className="w-full font-black text-sm bg-transparent focus:outline-none"
                        />
                      </div>
                      <div className="bg-white p-3 rounded-2xl border-2 border-black">
                        <label className="block text-[9px] font-black text-slate-500 mb-1">Mục tiêu (kg)</label>
                        <input 
                          type="number" 
                          value={targetWeight}
                          onChange={e => setTargetWeight(e.target.value)}
                          className="w-full font-black text-sm bg-transparent focus:outline-none"
                        />
                      </div>
                    </div>

                    <button 
                      onClick={handleAiDietAdvise}
                      disabled={isAiDietLoading}
                      className="w-full bg-sky-300 hover:bg-sky-400 text-slate-900 border-2 border-black font-black py-2.5 rounded-xl shadow-[2px_2px_0_0_#000] text-xs transition-all flex items-center justify-center gap-1"
                    >
                      {isAiDietLoading ? 'Đang phân tích...' : '⚡ Nhận Thực Đơn Giảm Cân Từ Snoopy AI 🍉'}
                    </button>

                    {bmi && (
                      <div className="bg-[#FFFDF5] text-slate-900 p-4 rounded-2xl border-2 border-black shadow-[4px_4px_0_0_#000]">
                        <div className="flex items-baseline gap-1.5">
                          <span className="text-xs font-black text-slate-500">Chỉ số BMI của bạn:</span>
                          <span className="text-2xl font-black text-teal-700">{bmi}</span>
                        </div>
                        <div className="bg-white p-3 rounded-lg border border-slate-200 text-xs font-bold text-slate-700 leading-relaxed whitespace-pre-wrap mt-2">
                          {dietSuggestion}
                        </div>
                      </div>
                    )}
                  </section>
                </div>

                <div className="lg:col-span-5">
                  <section className="bg-gradient-to-br from-blue-600 to-indigo-700 text-white p-6 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4 flex flex-col justify-between relative overflow-hidden">
                    <div>
                      <h2 className="text-xl font-black text-white flex items-center gap-1.5">
                        <Droplet className="text-sky-300 fill-sky-300 animate-pulse" size={20}/> Nhu Cầu Nước Theo BMI & Giảm Cân
                      </h2>
                      <p className="text-xs text-blue-100 mt-1">
                        Mục tiêu uống nước: <span className="font-bold underline text-yellow-300">{targetWaterLiters} Lít</span> (~ {targetWaterGlasses} cốc) mỗi ngày để hỗ trợ cơ bắp và đào thải mỡ thừa giảm cân!
                      </p>
                    </div>

                    <div className="flex justify-center py-2 relative">
                      <div className="relative w-28 h-36 bg-white/20 border-4 border-white rounded-b-3xl overflow-hidden shadow-inner flex items-end">
                        <div 
                          className="absolute w-full bg-sky-400 border-t-2 border-white transition-all duration-700 animate-pulse"
                          style={{ height: `${(waterGlasses / targetWaterGlasses) * 100}%` }}
                        >
                          {waterGlasses > 0 && (
                            <div className="w-full h-2 bg-sky-300 opacity-60 animate-pulse absolute top-0 left-0"></div>
                          )}
                        </div>
                        <div className="absolute inset-0 flex items-center justify-center font-black text-white text-xl z-10 drop-shadow-md">
                          {waterGlasses}/{targetWaterGlasses} Cốc
                        </div>
                      </div>
                    </div>

                    <div className="flex gap-2">
                      <button 
                        onClick={() => adjustWater(1)}
                        className="flex-1 bg-yellow-300 hover:bg-yellow-400 text-slate-900 border-2 border-black font-black py-2 rounded-xl text-xs shadow-[2px_2px_0_0_#000]"
                      >
                        + Đã Uống 1 Cốc 💧
                      </button>
                      <button 
                        onClick={() => adjustWater(-1)}
                        className="bg-white/20 hover:bg-white/30 border border-white/40 font-bold px-2.5 rounded-xl text-[10px]"
                      >
                        Bớt cốc
                      </button>
                    </div>
                  </section>
                </div>

              </div>

              {/* 🏋️‍♂️ MỤC TẬP THỂ DỤC (SNOOPY FITNESS LAB) */}
              <div className="grid grid-cols-1 lg:grid-cols-12 gap-6">
                
                <div className="lg:col-span-5">
                  <section className="bg-white p-6 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                    <h3 className="text-lg font-black text-slate-900 flex items-center gap-1.5">
                      <Dumbbell className="text-emerald-500 animate-bounce" /> Thêm Bài Tập Mới
                    </h3>

                    <form onSubmit={handleAddWorkoutRoutine} className="space-y-3">
                      <div>
                        <label className="block text-[10px] font-black text-slate-500 mb-0.5">Tên bài tập</label>
                        <input 
                          type="text"
                          placeholder="VD: Nhảy Cardio đốt mỡ, Gập bụng..."
                          value={newWorkoutName}
                          onChange={e => setNewWorkoutName(e.target.value)}
                          className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-2 focus:outline-none"
                        />
                      </div>

                      <div className="grid grid-cols-2 gap-2">
                        <div>
                          <label className="block text-[10px] font-black text-slate-500 mb-0.5">Số hiệp (Sets)</label>
                          <input 
                            type="text"
                            placeholder="VD: 3 hiệp, 5 hiệp..."
                            value={newWorkoutSets}
                            onChange={e => setNewWorkoutSets(e.target.value)}
                            className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-2 focus:outline-none"
                          />
                        </div>
                        <div>
                          <label className="block text-[10px] font-black text-slate-500 mb-0.5">Số lần/Thời gian (Reps)</label>
                          <input 
                            type="text"
                            placeholder="VD: 15 lần, 45 giây..."
                            value={newWorkoutReps}
                            onChange={e => setNewWorkoutReps(e.target.value)}
                            className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-2 focus:outline-none"
                          />
                        </div>
                      </div>

                      <div>
                        <label className="block text-[10px] font-black text-slate-500 mb-0.5">Đường dẫn Link hướng dẫn tập (Video/Youtube)</label>
                        <input 
                          type="text"
                          placeholder="Dán link tập luyện tại đây..."
                          value={newWorkoutLink}
                          onChange={e => setNewWorkoutLink(e.target.value)}
                          className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-2 focus:outline-none"
                        />
                      </div>

                      <button type="submit" className="w-full bg-[#A7F3D0] border-2 border-black hover:bg-emerald-300 font-black text-xs py-2.5 rounded-xl shadow-[2px_2px_0_0_#000] transition-all">
                        + Lưu Vào Giáo Án Thể Chất
                      </button>
                    </form>
                  </section>
                </div>

                <div className="lg:col-span-7">
                  <section className="bg-slate-50 p-6 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                    <h3 className="text-lg font-black text-slate-900 flex items-center gap-1.5">
                      🏋️‍♂️ Nhật Ký Giáo Án Thể Chất (Snoopy Gym)
                    </h3>
                    <p className="text-[10px] text-slate-500 font-bold">Lên danh sách tập, bấm gạch chéo khi tập xong và nhấp link mở video tập cực thảnh thơi!</p>

                    <div className="space-y-3 max-h-80 overflow-y-auto pr-1">
                      {workoutRoutines.map(routine => (
                        <div 
                          key={routine.id}
                          className={`flex items-center justify-between p-3 rounded-2xl border-2 transition-all ${
                            routine.completed 
                            ? 'bg-slate-200 border-slate-300 opacity-60' 
                            : 'bg-white border-black shadow-[2px_2px_0_0_#000] hover:-translate-y-0.5'
                          }`}
                        >
                          <div className="flex items-center gap-3">
                            <button
                              onClick={() => handleToggleWorkout(routine.id)}
                              className={`w-6 h-6 rounded-lg border-2 flex items-center justify-center transition-all ${
                                routine.completed 
                                ? 'bg-emerald-400 border-emerald-400 text-white' 
                                : 'border-black bg-white hover:bg-slate-100'
                              }`}
                            >
                              {routine.completed && <Check size={14} strokeWidth={4} />}
                            </button>
                            <div>
                              <span className={`block text-xs font-black ${routine.completed ? 'line-through text-slate-400' : 'text-slate-800'}`}>
                                {routine.name}
                              </span>
                              <span className="block text-[10px] text-slate-500 font-semibold">
                                {routine.sets} • {routine.reps}
                              </span>
                            </div>
                          </div>

                          <div className="flex items-center gap-2">
                            {routine.link && (
                              <a 
                                href={routine.link} 
                                target="_blank" 
                                rel="noopener noreferrer" 
                                className="bg-sky-100 text-sky-800 border border-sky-300 font-bold text-[9px] px-2 py-1 rounded-lg hover:bg-sky-200 flex items-center gap-1 shadow-sm"
                              >
                                <ExternalLink size={10}/> Tập Ngay
                              </a>
                            )}
                            <button 
                              onClick={() => handleDeleteWorkout(routine.id)}
                              className="text-slate-400 hover:text-red-500"
                            >
                              <Trash2 size={14} />
                            </button>
                          </div>
                        </div>
                      ))}

                      {workoutRoutines.length === 0 && (
                        <div className="text-center py-12 border-2 border-dashed border-slate-200 rounded-3xl bg-white">
                          <p className="text-xs font-bold text-slate-400">Bạn chưa có bài tập nào. Hãy lập giáo án thể chất của riêng bạn nhé!</p>
                        </div>
                      )}
                    </div>
                  </section>
                </div>

              </div>

            </div>
          )}

          {/* Tab Nhật Ký Động Lực (Snoopy Journal & Inspiring Images) */}
          {activeTab === 'motivation' && (
            <div className="grid grid-cols-1 lg:grid-cols-12 gap-6">
              
              <div className="lg:col-span-6 space-y-6">
                
                <section className="bg-white p-6 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                  <div className="flex items-center gap-2 border-b-2 border-dashed border-slate-100 pb-3">
                    <span className="text-3xl">📔</span>
                    <div>
                      <h2 className="text-xl font-black text-slate-900">Góc Nhật Ký Động Lực</h2>
                      <p className="text-xs font-bold text-slate-400">Viết nhật kỳ và đăng tải những bức ảnh tạo cảm hứng cho bạn!</p>
                    </div>
                  </div>

                  <form onSubmit={handleAddJournalEntry} className="space-y-3">
                    <div>
                      <label className="block text-xs font-black text-slate-500 mb-1">Cảm xúc của bạn hôm nay thế nào?</label>
                      <select 
                        value={newJournalMood}
                        onChange={e => setNewJournalMood(e.target.value)}
                        className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl px-3 py-2 focus:outline-none"
                      >
                        <option value="🌟 Rất Tốt">🌟 Rất Tốt - Tràn ngập năng lượng</option>
                        <option value="🐶 Thư Thái">🐶 Thư Thái - Đang đi đúng hướng</option>
                        <option value="🍂 Hơi Mệt">🍂 Hơi Mệt - Cần Snoopy khích lệ</option>
                        <option value="🧠 Mất Tập Trung">🧠 Mất Tập Trung - Cần Pomodoro trợ giúp</option>
                      </select>
                    </div>

                    <div>
                      <label className="block text-xs font-black text-slate-500 mb-1">Nhập nội dung nhật ký</label>
                      <textarea 
                        rows="3"
                        placeholder="Hôm nay bạn đã hoàn thành nhiệm vụ nào làm bản thân tự hào không?"
                        value={newJournalText}
                        onChange={e => setNewJournalText(e.target.value)}
                        className="w-full font-bold text-xs bg-slate-50 border-2 border-black rounded-xl p-3 focus:outline-none focus:bg-white resize-none"
                      />
                    </div>

                    <div className="space-y-2">
                      <label className="block text-xs font-black text-slate-500 mb-1">Tải ảnh truyền cảm hứng của bạn</label>
                      <div className="flex items-center gap-3">
                        <button
                          type="button"
                          onClick={() => fileInputRef.current?.click()}
                          className="bg-slate-100 hover:bg-slate-200 border-2 border-black text-slate-800 text-xs font-black px-4 py-2 rounded-xl flex items-center gap-1.5 transition-all shadow-sm"
                        >
                          <ImageIcon size={14}/> Chọn ảnh động lực
                        </button>
                        <input 
                          type="file"
                          ref={fileInputRef}
                          onChange={handleImageChange}
                          accept="image/*"
                          className="hidden"
                        />
                      </div>

                      {journalImagePreview && (
                        <div className="relative w-full max-h-40 rounded-xl overflow-hidden border-2 border-black mt-2">
                          <img src={journalImagePreview} alt="Preview" className="w-full h-full object-cover"/>
                          <button
                            type="button"
                            onClick={() => setJournalImagePreview(null)}
                            className="absolute top-2 right-2 bg-red-500 text-white rounded-full p-1"
                          >
                            <Trash size={14}/>
                          </button>
                        </div>
                      )}
                    </div>

                    <button 
                      type="submit"
                      className="w-full bg-[#A7F3D0] hover:bg-emerald-300 text-slate-900 border-2 border-black font-black py-2.5 rounded-xl text-xs shadow-[2px_2px_0_0_#000] transition-all"
                    >
                      Lưu Vào Nhật Ký Động Lực 🐾
                    </button>
                  </form>
                </section>

              </div>

              <div className="lg:col-span-6 space-y-6">
                <section className="bg-[#FFFDF5] p-6 rounded-[2.5rem] border-4 border-black shadow-[6px_6px_0_0_#000] space-y-4">
                  <h3 className="text-lg font-black text-slate-900 flex items-center gap-2">
                    <Calendar className="text-yellow-500" size={20}/> Sổ Hoạt Động & Hình Ảnh Truyền Cảm Hứng
                  </h3>

                  <div className="space-y-4 max-h-[500px] overflow-y-auto pr-2">
                    {journalEntries.map(entry => (
                      <div key={entry.id} className="bg-white p-4 rounded-2xl border-2 border-black shadow-[3px_3px_0_0_#000] relative">
                        <button
                          onClick={() => setJournalEntries(journalEntries.filter(e => e.id !== entry.id))}
                          className="absolute top-3 right-3 text-slate-400 hover:text-red-500"
                        >
                          <Trash size={16}/>
                        </button>

                        <div className="flex items-center gap-2 mb-2">
                          <span className="bg-yellow-100 text-yellow-800 text-[10px] font-black px-2 py-0.5 rounded border border-yellow-200">
                            {entry.date}
                          </span>
                          <span className="bg-indigo-100 text-indigo-800 text-[10px] font-black px-2 py-0.5 rounded border border-indigo-200">
                            Tâm trạng: {entry.mood}
                          </span>
                        </div>

                        <p className="text-xs font-bold text-slate-700 leading-relaxed mb-3 whitespace-pre-wrap">
                          {entry.text}
                        </p>

                        {entry.image && (
                          <div className="mt-2 rounded-xl overflow-hidden border border-black max-h-48">
                            <img src={entry.image} alt="Motivator" className="w-full h-full object-cover"/>
                          </div>
                        )}
                      </div>
                    ))}

                    {journalEntries.length === 0 && (
                      <div className="text-center py-12 border-2 border-dashed border-slate-200 rounded-3xl">
                        <Smile size={32} className="mx-auto text-slate-400 mb-2"/>
                        <p className="font-black text-sm text-slate-500">Hãy tự tay viết trang nhật ký đầu tiên để khích lệ bản thân nhé!</p>
                      </div>
                    )}
                  </div>
                </section>
              </div>

            </div>
          )}

          {/* Tab Màn Hình Khóa Zen Saver (image_cbeacd.png) */}
          {activeTab === 'lockscreen' && (
            <div className="max-w-xl mx-auto bg-slate-950 text-slate-100 p-6 rounded-[3rem] border-8 border-black shadow-[8px_8px_0_0_#000] relative">
              <div className="flex justify-between items-center text-[10px] font-black text-slate-500 mb-6">
                <span>📶 VNPT 5G</span>
                <span>85% 🔋</span>
              </div>

              <div className="text-center space-y-1 mb-8">
                <span className="text-5xl font-black tracking-widest text-yellow-300 block">
                  {lockTime || '12:00:00'}
                </span>
                <span className="text-[10px] font-bold text-slate-400 block uppercase tracking-wider">
                  Snoopy Screen Saver • Chống Xao Nhãng
                </span>
              </div>

              <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 mb-6 text-center space-y-2">
                <span className="text-4xl animate-bounce block">💤🐶😴</span>
                <input 
                  type="text" 
                  value={lockscreenSlogan}
                  onChange={(e) => setLockscreenSlogan(e.target.value)}
                  className="w-full bg-transparent border-none text-[11px] font-bold text-slate-300 text-center focus:outline-none"
                  placeholder="Viết châm ngôn chống xao nhãng của riêng bạn..."
                />
              </div>

              <div className="space-y-2 mb-6">
                <h4 className="text-xs font-black flex items-center gap-1.5 text-yellow-300">
                  <Pin size={12} className="text-yellow-300 fill-yellow-300"/> GHI CHÚ MÀN HÌNH KHÓA (PINNED NOTES)
                </h4>

                <div className="space-y-1.5 max-h-40 overflow-y-auto pr-1">
                  {lockscreenNotes.map(note => (
                    <div key={note.id} className="flex justify-between items-center p-2.5 rounded-lg bg-slate-900 border border-slate-800 text-xs">
                      <span className="font-medium text-slate-300">{note.text}</span>
                      <button onClick={() => setLockscreenNotes(lockscreenNotes.filter(n => n.id !== note.id))} className="text-[10px] font-black text-red-400 hover:underline">
                        Xóa
                      </button>
                    </div>
                  ))}
                </div>

                <form onSubmit={handleAddLockNote} className="flex gap-2">
                  <input 
                    type="text" 
                    value={newLockNote}
                    onChange={e => setNewLockNote(e.target.value)}
                    placeholder="Ghi nhanh việc quan trọng vào đây..."
                    className="flex-1 font-bold text-xs bg-slate-900 border border-slate-700 rounded-lg px-3 py-1.5 focus:outline-none text-white"
                  />
                  <button type="submit" className="bg-yellow-300 text-slate-900 font-black text-xs px-3 rounded-lg">Ghim</button>
                </form>
              </div>

              <div className="text-center">
                <button 
                  onClick={() => { setActiveTab('map'); playAudioFeedback('click', isMuted); }}
                  className="mx-auto bg-white hover:bg-slate-100 text-slate-900 font-black text-xs px-5 py-2 rounded-full border-2 border-black flex items-center gap-1"
                >
                  <Unlock size={12}/> Quay lại Dashboard
                </button>
              </div>
            </div>
          )}

        </main>

        {/* Footer (image_cb020e.png) */}
        <div className="flex flex-col items-center mt-12 gap-4">
          
          <div className="flex justify-center items-center gap-2 md:gap-4 flex-wrap bg-white border-4 border-black p-3 rounded-[1.5rem] shadow-[4px_4px_0_0_#000]">
            {['T2', 'T3', 'T4', 'T5', 'T6', 'T7', 'CN'].map((day) => {
              const trackingDay = weeklyData.find(w => w.day === day);
              const minutes = trackingDay ? trackingDay.val : 0;
              return (
                <div key={day} className="flex flex-col items-center">
                  <button 
                    onClick={() => {
                      updateWeeklyFocus(15);
                      triggerDopamine(`Đã nạp thêm 15 phút tập trung cho ngày ${day}! ⚡`, 3);
                    }}
                    className={`px-3 py-1.5 rounded-lg border-2 border-black text-xs font-black transition-all hover:scale-105 active:scale-95 shadow-[1px_1px_0_0_#000] ${minutes > 0 ? 'bg-emerald-300 text-slate-900' : 'bg-white text-slate-700'}`}
                  >
                    {day}
                  </button>
                  <span className="text-[9px] font-black text-slate-400 mt-1">{minutes}p</span>
                </div>
              );
            })}
          </div>

          <div className="w-full max-w-2xl bg-white rounded-[2rem] border-4 border-black p-5 shadow-[6px_6px_0_0_#000] relative text-center">
            <div className="absolute top-2 left-3 opacity-30 pointer-events-none text-xs">🐾🐾</div>
            
            <div className="flex items-center gap-2 justify-center">
              <Edit3 size={14} className="text-slate-400 shrink-0" />
              <input 
                type="text"
                value={footerQuote}
                onChange={(e) => setFooterQuote(e.target.value)}
                placeholder="Hãy viết câu nói động viên của bạn tại đây để Snoopy reo hò nhé... ✍️"
                className="w-full bg-transparent border-none text-slate-700 text-xs md:text-sm font-black focus:outline-none placeholder-slate-400 text-center leading-relaxed"
              />
            </div>
          </div>

        </div>

      </div>
    </div>
  );
}
                  // 1. TÁCH CHỨC NĂNG ĐỒNG HỒ POMODORO THÀNH COMPONENT RIÊNG (Đặt bên ngoài App component)
function PomodoroTimer({ triggerDopamine, gainXP, updateWeeklyFocus }) {
  const [timeLeft, setTimeLeft] = useState(25 * 60);
  const [isActive, setIsActive] = useState(false);
  const [timerMode, setTimerMode] = useState('focus');

  useEffect(() => {
    let interval = null;
    if (isActive && timeLeft > 0) {
      interval = setInterval(() => setTimeLeft(t => t - 1), 1000);
    } else if (timeLeft === 0 && isActive) {
      setIsActive(false);
      if (timerMode === 'focus') {
        setTimerMode('break'); setTimeLeft(5 * 60);
        triggerDopamine("Hoàn thành chu kỳ Focus!", 5, true);
        gainXP(50); updateWeeklyFocus(25);
      } else {
        setTimerMode('focus'); setTimeLeft(25 * 60);
        triggerDopamine("Hết giờ nghỉ! Quay lại làm việc nào!", 3);
      }
    }
    return () => clearInterval(interval);
  }, [isActive, timeLeft, timerMode]);

  return (
    <div className="bg-white p-8 rounded-3xl border border-slate-100 shadow-sm text-center max-w-md mx-auto">
      <h2 className="text-2xl font-bold text-slate-800 mb-2 flex items-center justify-center gap-2"><Zap className="text-orange-500"/> Focus Timer</h2>
      <p className="text-slate-500 text-sm mb-8">Chế độ: {timerMode === 'focus' ? 'Tập trung (25 phút)' : 'Nghỉ ngơi (5 phút)'}</p>
      
      <div className="text-7xl font-black text-indigo-600 mb-8 tracking-tighter">
        {Math.floor(timeLeft / 60).toString().padStart(2, '0')}:{(timeLeft % 60).toString().padStart(2, '0')}
      </div>
      
      <div className="flex justify-center gap-4">
        <button onClick={() => setIsActive(!isActive)} className={`px-8 py-3 font-bold rounded-2xl text-white shadow-md transition-all ${isActive ? 'bg-rose-500 hover:bg-rose-600 shadow-rose-200' : 'bg-indigo-600 hover:bg-indigo-700 shadow-indigo-200'}`}>
          {isActive ? 'Tạm Dừng' : 'Bắt Đầu'}
        </button>
        <button onClick={() => { setIsActive(false); setTimeLeft(timerMode === 'focus' ? 25 * 60 : 5 * 60); }} className="px-6 py-3 bg-slate-100 hover:bg-slate-200 text-slate-700 font-bold rounded-2xl transition-all">
          Reset
        </button>
      </div>
    </div>
  );
}

// 2. TÁCH CHỨC NĂNG BIỂU ĐỒ MỤC TIÊU THÀNH COMPONENT RIÊNG (Đặt bên ngoài App component)
function GoalProgressChart({ monthlyGoals }) {
  return (
    <div className="bg-white p-6 rounded-3xl border border-slate-100 shadow-sm">
      <h3 className="font-bold text-slate-800 mb-6 flex items-center gap-2"><BarChart2 className="text-indigo-500" size={18}/> Biểu Đồ Tiến Độ Mục Tiêu</h3>
      <div className="flex items-end gap-4 h-48 mt-4 pt-4 border-l border-b border-slate-200 relative pb-2 pl-2">
        <div className="absolute top-0 left-[-30px] h-full flex flex-col justify-between text-[10px] text-slate-400 font-medium pb-2">
          <span>100%</span>
          <span>50%</span>
          <span>0%</span>
        </div>
        
        <div className="absolute inset-0 border-b border-slate-100 top-[50%] pointer-events-none"></div>
        <div className="absolute inset-0 border-b border-slate-100 top-[0%] pointer-events-none"></div>

        {monthlyGoals.map(goal => {
          const pct = Math.min((goal.currentValue / goal.targetValue) * 100, 100);
          return (
            <div key={goal.id} className="flex-1 flex flex-col items-center justify-end h-full relative group">
              <div className="w-full max-w-[40px] bg-indigo-50 rounded-t-md relative h-full border border-indigo-100 border-b-0">
                 <div 
                    className={`absolute bottom-0 w-full rounded-t-md transition-all duration-1000 ${pct >= 100 ? 'bg-emerald-500 shadow-[0_0_10px_rgba(16,185,129,0.4)]' : 'bg-gradient-to-t from-indigo-500 to-indigo-400'}`} 
                    style={{ height: `${pct}%` }}
                 ></div>
              </div>
              <div className="absolute -top-10 bg-slate-800 text-white text-[10px] py-1 px-2 rounded opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none whitespace-nowrap z-10">
                {goal.title}: {Math.round(pct)}%
              </div>
              <span className="text-[10px] font-semibold text-slate-500 mt-2 truncate w-full text-center px-1" title={goal.title}>{goal.title}</span>
            </div>
          );
        })}
      </div>
    </div>
  );
}

// 3. CODE THAY ĐỔI TRONG HÀM APP() CHÍNH ĐỂ MỞ MẶC ĐỊNH TAB TÀI CHÍNH (Thay cho màn hình khóa)
export default function App() {
  // ... (giữ nguyên các state cũ)

  // Bỏ màn hình khóa, mặc định vào thẳng
  const [activeRoom, setActiveRoom] = useState('default_workspace'); 

  // Thay thế chức năng màn hình khóa thành mở mặc định tab Quản lý chi tiêu (Finance)
  const [activeTab, setActiveTab] = useState('finance'); 

  // ... (giữ nguyên các đoạn code tiếp theo của bạn)
                  import React, { useState } from 'react';
import { Calendar } from 'lucide-react'; // Đảm bảo bạn đã cài lucide-react hoặc thay bằng icon bạn thích

// TÁCH CHỨC NĂNG THỜI KHÓA BIỂU THÀNH COMPONENT RIÊNG
export default function WeeklySchedule() {
  // Dữ liệu mẫu (bạn có thể thay đổi sau để phù hợp với lịch thực tế)
  const [schedule, setSchedule] = useState([
    { id: 1, day: 'Thứ 2', time: 'Sáng', task: 'Toán & Vật Lý Nâng Cao', color: 'bg-pink-100 text-pink-700 border-pink-200' },
    { id: 2, day: 'Thứ 2', time: 'Chiều', task: 'Học từ vựng Anki & BBC', color: 'bg-blue-100 text-blue-700 border-blue-200' },
    { id: 3, day: 'Thứ 3', time: 'Sáng', task: 'Sinh Học Nâng Cao', color: 'bg-green-100 text-green-700 border-green-200' },
    { id: 4, day: 'Thứ 3', time: 'Tối', task: 'Dự án Nghiên cứu In silico', color: 'bg-purple-100 text-purple-700 border-purple-200' },
    { id: 5, day: 'Thứ 4', time: 'Sáng', task: 'Hóa Học', color: 'bg-yellow-100 text-yellow-700 border-yellow-200' },
    { id: 6, day: 'Thứ 5', time: 'Chiều', task: 'Chuẩn bị hồ sơ MEXT', color: 'bg-orange-100 text-orange-700 border-orange-200' },
    { id: 7, day: 'Thứ 6', time: 'Tối', task: 'TED Talks & Luyện nghe', color: 'bg-blue-100 text-blue-700 border-blue-200' },
    { id: 8, day: 'Thứ 7', time: 'Chiều', task: 'Chụp ảnh Film 35mm', color: 'bg-teal-100 text-teal-700 border-teal-200' },
    { id: 9, day: 'CN', time: 'Sáng', task: 'Tổng hợp tài liệu Notion', color: 'bg-rose-100 text-rose-700 border-rose-200' },
  ]);

  const days = ['Thứ 2', 'Thứ 3', 'Thứ 4', 'Thứ 5', 'Thứ 6', 'Thứ 7', 'CN'];
  const times = ['Sáng', 'Chiều', 'Tối'];

  return (
    <div className="bg-white p-8 rounded-3xl border border-slate-100 shadow-sm w-full font-serif">
      <h2 className="text-2xl font-bold text-slate-800 mb-6 flex items-center gap-2">
        <Calendar className="text-pink-400" size={24} /> Thời Gian Biểu Tổng Thể
      </h2>
      
      <div className="overflow-x-auto">
        <table className="w-full min-w-[800px] border-collapse">
          <thead>
            <tr>
              <th className="p-3 border-b-2 border-slate-100 text-left text-slate-500 w-24">Ca học</th>
              {days.map(day => (
                <th key={day} className="p-3 border-b-2 border-slate-100 text-center text-slate-600 font-semibold w-32">
                  {day}
                </th>
              ))}
            </tr>
          </thead>
          <tbody>
            {times.map(time => (
              <tr key={time} className="border-b border-slate-50">
                <td className="p-3 font-medium text-slate-500 bg-slate-50/50">{time}</td>
                {days.map(day => {
                  const task = schedule.find(s => s.day === day && s.time === time);
                  return (
                    <td key={`${day}-${time}`} className="p-2 border-l border-slate-50 relative h-24 align-top">
                      {task ? (
                        <div className={`p-2 rounded-xl border ${task.color} h-full shadow-sm text-sm font-medium flex flex-col justify-center items-center text-center transition-all hover:scale-105 hover:shadow-md cursor-pointer`}>
                          {task.task}
                        </div>
                      ) : (
                        <div className="p-2 h-full rounded-xl border border-dashed border-slate-200 text-slate-300 flex items-center justify-center text-xs hover:bg-slate-50 transition-colors cursor-pointer">
                          + Trống
                        </div>
                      )}
                    </td>
                  );
                })}
              </tr>
            ))}
          </tbody>
        </table>
      </div>
    </div>
  );
}

import React, { useState, useEffect, useRef, createContext, useContext } from 'react';
import { initializeApp } from 'firebase/app';
import { 
    getAuth, 
    onAuthStateChanged, 
    createUserWithEmailAndPassword, 
    signInWithEmailAndPassword, 
    signOut,
    updateProfile,
    signInWithCustomToken,
    signInAnonymously
} from 'firebase/auth';
import { 
    getFirestore, 
    collection, 
    addDoc, 
    query, 
    orderBy, 
    onSnapshot, 
    doc, 
    getDoc, 
    updateDoc,
    setDoc,
    deleteDoc,
    serverTimestamp,
    arrayUnion,
    arrayRemove,
    writeBatch,
    getDocs,
    where,
    limit
} from 'firebase/firestore';
import { Home, Bell, User, Settings, Search, Image as ImageIcon, X, Heart, MessageCircle, Repeat, LogOut, Loader2, PlusCircle, Globe } from 'lucide-react';

// --- MULTI-LANGUAGE SUPPORT (i18n) ---
const translations = {
    en: {
        // Auth
        'welcome': 'Welcome to SocialMy',
        'login_prompt': 'Log in to continue',
        'signup_prompt': 'Sign up to get started',
        'email': 'Email',
        'password': 'Password',
        'display_name': 'Display Name',
        'login': 'Log In',
        'signup': 'Sign Up',
        'no_account': "Don't have an account?",
        'have_account': 'Already have an account?',
        'logout': 'Log Out',
        'logging_in': 'Logging in...',
        'signing_up': 'Signing up...',
        // Navigation
        'home': 'Home',
        'search': 'Search',
        'notifications': 'Notifications',
        'profile': 'Profile',
        'post': 'Post',
        // Post Form
        'whats_happening': "What's happening?",
        'add_image': 'Add Image',
        'posting': 'Posting...',
        // Feed
        'feed_title': 'Home Feed',
        'load_more': 'Load More',
        // Interactions
        'like': 'Like',
        'comment': 'Comment',
        'repost': 'Repost',
        'comments': 'Comments',
        'add_comment': 'Add a comment...',
        'post_comment': 'Post Comment',
        // Profile
        'edit_profile': 'Edit Profile',
        'following': 'Following',
        'followers': 'Followers',
        'follow': 'Follow',
        'unfollow': 'Unfollow',
        'posts': 'Posts',
        // Notifications
        'new_like': 'liked your post.',
        'new_comment': 'commented on your post.',
        'new_follow': 'started following you.',
        'no_notifications': 'No new notifications.',
        // Search
        'search_users': 'Search for users...',
        'no_users_found': 'No users found.',
        // Who to follow
        'who_to_follow': 'Who to follow',
        // General
        'error_occurred': 'An error occurred. Please try again.',
        'success': 'Success!',
        'post_successful': 'Your post has been published!',
        'under_development': 'This feature is under development.',
    },
    zh: {
        // Auth
        'welcome': '欢迎来到 SocialMy',
        'login_prompt': '登录以继续',
        'signup_prompt': '注册以开始',
        'email': '电子邮件',
        'password': '密码',
        'display_name': '显示名称',
        'login': '登录',
        'signup': '注册',
        'no_account': '还没有账户？',
        'have_account': '已经有账户了？',
        'logout': '登出',
        'logging_in': '登录中...',
        'signing_up': '注册中...',
        // Navigation
        'home': '主页',
        'search': '搜索',
        'notifications': '通知',
        'profile': '个人资料',
        'post': '发布',
        // Post Form
        'whats_happening': '有什么新鲜事？',
        'add_image': '添加图片',
        'posting': '发布中...',
        // Feed
        'feed_title': '主页动态',
        'load_more': '加载更多',
        // Interactions
        'like': '喜欢',
        'comment': '评论',
        'repost': '转发',
        'comments': '评论',
        'add_comment': '添加评论...',
        'post_comment': '发表评论',
        // Profile
        'edit_profile': '编辑个人资料',
        'following': '关注中',
        'followers': '粉丝',
        'follow': '关注',
        'unfollow': '取消关注',
        'posts': '帖子',
        // Notifications
        'new_like': '喜欢了你的帖子。',
        'new_comment': '评论了你的帖子。',
        'new_follow': '开始关注你了。',
        'no_notifications': '暂无新通知。',
        // Search
        'search_users': '搜索用户...',
        'no_users_found': '未找到用户。',
        // Who to follow
        'who_to_follow': '推荐关注',
        // General
        'error_occurred': '发生错误，请重试。',
        'success': '成功！',
        'post_successful': '您的帖子已发布！',
        'under_development': '此功能正在开发中。',
    },
    ja: {
        // Auth
        'welcome': 'SocialMyへようこそ',
        'login_prompt': 'ログインして続行',
        'signup_prompt': 'サインアップして開始',
        'email': 'Eメール',
        'password': 'パスワード',
        'display_name': '表示名',
        'login': 'ログイン',
        'signup': 'サインアップ',
        'no_account': 'アカウントをお持ちではありませんか？',
        'have_account': 'すでにアカウントをお持ちですか？',
        'logout': 'ログアウト',
        'logging_in': 'ログイン中...',
        'signing_up': 'サインアップ中...',
        // Navigation
        'home': 'ホーム',
        'search': '検索',
        'notifications': '通知',
        'profile': 'プロフィール',
        'post': '投稿',
        // Post Form
        'whats_happening': 'どうしましたか？',
        'add_image': '画像を追加',
        'posting': '投稿中...',
        // Feed
        'feed_title': 'ホームフィード',
        'load_more': 'もっと読み込む',
        // Interactions
        'like': 'いいね',
        'comment': 'コメント',
        'repost': 'リポスト',
        'comments': 'コメント',
        'add_comment': 'コメントを追加...',
        'post_comment': 'コメントを投稿',
        // Profile
        'edit_profile': 'プロフィールを編集',
        'following': 'フォロー中',
        'followers': 'フォロワー',
        'follow': 'フォロー',
        'unfollow': 'フォロー解除',
        'posts': '投稿',
        // Notifications
        'new_like': 'があなたの投稿に「いいね」しました。',
        'new_comment': 'があなたの投稿にコメントしました。',
        'new_follow': 'があなたをフォローし始めました。',
        'no_notifications': '新しい通知はありません。',
        // Search
        'search_users': 'ユーザーを検索...',
        'no_users_found': 'ユーザーが見つかりません。',
        // Who to follow
        'who_to_follow': 'おすすめユーザー',
        // General
        'error_occurred': 'エラーが発生しました。もう一度お試しください。',
        'success': '成功しました！',
        'post_successful': '投稿が公開されました！',
        'under_development': 'この機能は開発中です。',
    },
};

const LanguageContext = createContext();
const useTranslation = () => {
    const context = useContext(LanguageContext);
    if (!context) {
        throw new Error('useTranslation must be used within a LanguageProvider');
    }
    const { language, setLanguage } = context;
    const t = (key) => translations[language][key] || key;
    return { t, setLanguage, language };
};

const LanguageProvider = ({ children }) => {
    const [language, setLanguage] = useState('en');
    return (
        <LanguageContext.Provider value={{ language, setLanguage }}>
            {children}
        </LanguageContext.Provider>
    );
};

// --- NAVIGATION CONTEXT ---
const NavigationContext = createContext();
const useNavigation = () => useContext(NavigationContext);

const NavigationProvider = ({ children }) => {
    const [page, setPage] = useState('home');
    const [profileUser, setProfileUser] = useState(null);

    const navigate = (newPage, data = {}) => {
        if (newPage === 'profile') {
            setProfileUser(data.user);
        }
        setPage(newPage);
    };

    return (
        <NavigationContext.Provider value={{ page, profileUser, navigate }}>
            {children}
        </NavigationContext.Provider>
    );
};


// --- FIREBASE CONFIGURATION & HOOKS ---
const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : {};
const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-social-app';

const app = initializeApp(firebaseConfig);
const auth = getAuth(app);
const db = getFirestore(app);

const useAuth = () => {
    const [user, setUser] = useState(null);
    const [loading, setLoading] = useState(true);

    useEffect(() => {
        const unsubscribe = onAuthStateChanged(auth, async (firebaseUser) => {
            if (firebaseUser && firebaseUser.email) {
                const userRef = doc(db, `/artifacts/${appId}/public/data/users/${firebaseUser.uid}`);
                const unsubscribeProfile = onSnapshot(userRef, (userSnap) => {
                     if (userSnap.exists()) {
                        setUser({ uid: firebaseUser.uid, ...firebaseUser, ...userSnap.data() });
                    } else {
                        setUser(firebaseUser);
                    }
                    setLoading(false);
                });
                return () => unsubscribeProfile();
            } else {
                setUser(null);
                setLoading(false);
            }
        });

        const initialAuth = async () => {
            try {
                if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
                    await signInWithCustomToken(auth, __initial_auth_token);
                } else if (!auth.currentUser) {
                    await signInAnonymously(auth);
                }
            } catch (error) {
                console.error("Error during initial sign-in:", error);
            }
        };

        initialAuth();
        return () => unsubscribe();
    }, []);

    return { user, loading };
};


// --- MOCK IMAGE UPLOAD SERVICE ---
const uploadImageMock = async (file) => {
    return new Promise(resolve => {
        setTimeout(() => {
            const randomId = Math.random().toString(36).substring(7);
            const mockUrl = `https://placehold.co/600x400/1a1a1a/ffffff?text=${randomId}`;
            resolve(mockUrl);
        }, 1500);
    });
};

// --- API HELPER FUNCTIONS ---
const api = {
    createUserProfile: async (user, displayName) => {
        const userRef = doc(db, `/artifacts/${appId}/public/data/users/${user.uid}`);
        await setDoc(userRef, {
            displayName: displayName,
            email: user.email,
            photoURL: `https://i.pravatar.cc/150?u=${user.uid}`,
            following: [],
            followers: [],
            createdAt: serverTimestamp(),
        });
    },
    createPost: async (author, text, imageUrls) => {
        const postsCollection = collection(db, `/artifacts/${appId}/public/data/posts`);
        await addDoc(postsCollection, {
            authorId: author.uid,
            authorName: author.displayName,
            authorPhotoURL: author.photoURL,
            text,
            imageUrls,
            timestamp: serverTimestamp(),
            likes: [],
            commentsCount: 0,
            repostsCount: 0,
        });
    },
    toggleLike: async (postId, userId) => {
        const postRef = doc(db, `/artifacts/${appId}/public/data/posts/${postId}`);
        const postSnap = await getDoc(postRef);
        if (postSnap.exists()) {
            const postData = postSnap.data();
            const isLiked = postData.likes.includes(userId);
            if (isLiked) {
                await updateDoc(postRef, { likes: arrayRemove(userId) });
            } else {
                await updateDoc(postRef, { likes: arrayUnion(userId) });
                if (postData.authorId !== userId) {
                    await api.createNotification(postData.authorId, userId, 'like', postId);
                }
            }
        }
    },
    addComment: async (postId, author, text) => {
        const commentsCollection = collection(db, `/artifacts/${appId}/public/data/posts/${postId}/comments`);
        await addDoc(commentsCollection, {
            authorId: author.uid,
            authorName: author.displayName,
            authorPhotoURL: author.photoURL,
            text,
            timestamp: serverTimestamp(),
        });
        const postRef = doc(db, `/artifacts/${appId}/public/data/posts/${postId}`);
        const postSnap = await getDoc(postRef);
        if (postSnap.exists()) {
            const postData = postSnap.data();
            await updateDoc(postRef, { commentsCount: (postData.commentsCount || 0) + 1 });
            if (postData.authorId !== author.uid) {
                await api.createNotification(postData.authorId, author.uid, 'comment', postId);
            }
        }
    },
    toggleFollow: async (currentUser, targetUserId) => {
        const batch = writeBatch(db);
        const currentUserRef = doc(db, `/artifacts/${appId}/public/data/users/${currentUser.uid}`);
        const targetUserRef = doc(db, `/artifacts/${appId}/public/data/users/${targetUserId}`);

        const isFollowing = currentUser.following?.includes(targetUserId);

        if (isFollowing) {
            batch.update(currentUserRef, { following: arrayRemove(targetUserId) });
            batch.update(targetUserRef, { followers: arrayRemove(currentUser.uid) });
        } else {
            batch.update(currentUserRef, { following: arrayUnion(targetUserId) });
            batch.update(targetUserRef, { followers: arrayUnion(currentUser.uid) });
            await api.createNotification(targetUserId, currentUser.uid, 'follow');
        }
        await batch.commit();
    },
    createNotification: async (targetUserId, fromUserId, type, postId = null) => {
        const fromUserSnap = await getDoc(doc(db, `/artifacts/${appId}/public/data/users/${fromUserId}`));
        if (!fromUserSnap.exists()) return;

        const fromUserData = fromUserSnap.data();
        const notificationsCollection = collection(db, `/artifacts/${appId}/users/${targetUserId}/notifications`);
        
        await addDoc(notificationsCollection, {
            fromUserId,
            fromUserName: fromUserData.displayName,
            fromUserPhotoURL: fromUserData.photoURL,
            type,
            postId,
            timestamp: serverTimestamp(),
            read: false,
        });
    },
    getUser: async (userId) => {
        const userRef = doc(db, `/artifacts/${appId}/public/data/users/${userId}`);
        const userSnap = await getDoc(userRef);
        return userSnap.exists() ? { id: userSnap.id, ...userSnap.data() } : null;
    },
    searchUsers: async (searchTerm) => {
        if (!searchTerm) return [];
        const usersRef = collection(db, `/artifacts/${appId}/public/data/users`);
        const q = query(usersRef, where('displayName', '>=', searchTerm), where('displayName', '<=', searchTerm + '\uf8ff'));
        const querySnapshot = await getDocs(q);
        return querySnapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
    }
};

// --- UI COMPONENTS ---

const Spinner = () => <Loader2 className="animate-spin h-6 w-6 text-blue-500" />;

const AuthPage = () => {
    const [isLogin, setIsLogin] = useState(true);
    const [email, setEmail] = useState('');
    const [password, setPassword] = useState('');
    const [displayName, setDisplayName] = useState('');
    const [loading, setLoading] = useState(false);
    const [error, setError] = useState('');
    const { t } = useTranslation();

    const handleSubmit = async (e) => {
        e.preventDefault();
        setLoading(true);
        setError('');
        try {
            if (isLogin) {
                await signInWithEmailAndPassword(auth, email, password);
            } else {
                if (!displayName) {
                    setError('Display name is required.');
                    setLoading(false);
                    return;
                }
                const userCredential = await createUserWithEmailAndPassword(auth, email, password);
                await updateProfile(userCredential.user, { displayName });
                await api.createUserProfile(userCredential.user, displayName);
            }
        } catch (err) {
            setError(err.message);
        } finally {
            setLoading(false);
        }
    };
    
    return (
        <div className="min-h-screen bg-gray-900 text-white flex items-center justify-center p-4">
            <div className="w-full max-w-md bg-gray-800 p-8 rounded-2xl shadow-lg border border-gray-700">
                <h1 className="text-3xl font-bold text-center mb-2">{t('welcome')}</h1>
                <p className="text-center text-gray-400 mb-6">{isLogin ? t('login_prompt') : t('signup_prompt')}</p>
                
                <form onSubmit={handleSubmit}>
                    {!isLogin && (
                        <div className="mb-4">
                            <label className="block text-gray-400 mb-2" htmlFor="displayName">{t('display_name')}</label>
                            <input type="text" id="displayName" value={displayName} onChange={(e) => setDisplayName(e.target.value)} className="w-full bg-gray-700 border border-gray-600 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500" required />
                        </div>
                    )}
                    <div className="mb-4">
                        <label className="block text-gray-400 mb-2" htmlFor="email">{t('email')}</label>
                        <input type="email" id="email" value={email} onChange={(e) => setEmail(e.target.value)} className="w-full bg-gray-700 border border-gray-600 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500" required />
                    </div>
                    <div className="mb-6">
                        <label className="block text-gray-400 mb-2" htmlFor="password">{t('password')}</label>
                        <input type="password" id="password" value={password} onChange={(e) => setPassword(e.target.value)} className="w-full bg-gray-700 border border-gray-600 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500" required />
                    </div>
                    {error && <p className="text-red-500 text-sm mb-4">{error}</p>}
                    <button type="submit" disabled={loading} className="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-lg transition duration-300 flex items-center justify-center disabled:bg-blue-800 disabled:cursor-not-allowed">
                        {loading ? <Spinner /> : (isLogin ? t('login') : t('signup'))}
                    </button>
                </form>

                <p className="text-center text-gray-400 mt-6">
                    {isLogin ? t('no_account') : t('have_account')}{' '}
                    <button onClick={() => setIsLogin(!isLogin)} className="text-blue-500 hover:underline font-semibold">
                        {isLogin ? t('signup') : t('login')}
                    </button>
                </p>
            </div>
        </div>
    );
};

const PostForm = ({ user, onPost }) => {
    const [text, setText] = useState('');
    const [images, setImages] = useState([]);
    const [previews, setPreviews] = useState([]);
    const [isPosting, setIsPosting] = useState(false);
    const fileInputRef = useRef(null);
    const { t } = useTranslation();

    const handleImageChange = (e) => {
        if (e.target.files) {
            const filesArray = Array.from(e.target.files);
            if (images.length + filesArray.length > 4) {
                alert("You can only upload a maximum of 4 images.");
                return;
            }
            setImages(prev => [...prev, ...filesArray]);
            const newPreviews = filesArray.map(file => URL.createObjectURL(file));
            setPreviews(prev => [...prev, ...newPreviews]);
        }
    };
    
    const removeImage = (index) => {
        setImages(prev => prev.filter((_, i) => i !== index));
        setPreviews(prev => prev.filter((_, i) => i !== index));
    };

    const handleSubmit = async (e) => {
        e.preventDefault();
        if (!text.trim() && images.length === 0) return;
        
        setIsPosting(true);
        try {
            const imageUrls = await Promise.all(images.map(file => uploadImageMock(file)));
            await api.createPost(user, text, imageUrls);
            setText('');
            setImages([]);
            setPreviews([]);
            onPost();
        } catch (error) {
            console.error("Error creating post:", error);
        } finally {
            setIsPosting(false);
        }
    };

    return (
        <div className="p-4 border-b border-gray-700">
            <div className="flex space-x-4">
                <img src={user.photoURL} alt={user.displayName} className="h-12 w-12 rounded-full" />
                <div className="flex-1">
                    <form onSubmit={handleSubmit}>
                        <textarea
                            value={text}
                            onChange={(e) => setText(e.target.value)}
                            placeholder={t('whats_happening')}
                            className="w-full bg-transparent text-xl placeholder-gray-500 focus:outline-none resize-none"
                            rows="3"
                        ></textarea>
                        
                        {previews.length > 0 && (
                            <div className="mt-2 grid grid-cols-2 gap-2">
                                {previews.map((src, index) => (
                                    <div key={index} className="relative">
                                        <img src={src} alt="Preview" className="rounded-lg object-cover w-full h-32" />
                                        <button onClick={() => removeImage(index)} className="absolute top-1 right-1 bg-black bg-opacity-50 rounded-full p-1 text-white">
                                            <X size={16} />
                                        </button>
                                    </div>
                                ))}
                            </div>
                        )}

                        <div className="flex justify-between items-center mt-4">
                            <button type="button" onClick={() => fileInputRef.current.click()} className="text-blue-500 hover:text-blue-400">
                                <ImageIcon size={24} />
                            </button>
                            <input type="file" multiple accept="image/*" onChange={handleImageChange} ref={fileInputRef} className="hidden" />
                            <button type="submit" disabled={isPosting || (!text.trim() && images.length === 0)} className="bg-blue-600 text-white font-bold px-6 py-2 rounded-full disabled:opacity-50 disabled:cursor-not-allowed hover:bg-blue-700 transition">
                                {isPosting ? t('posting') : t('post')}
                            </button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    );
};

const Post = ({ post, currentUser }) => {
    const [isLiked, setIsLiked] = useState(false);
    const [comments, setComments] = useState([]);
    const [showComments, setShowComments] = useState(false);
    const [newComment, setNewComment] = useState('');
    const { t } = useTranslation();
    const { navigate } = useNavigation();

    useEffect(() => {
        setIsLiked(post.likes.includes(currentUser.uid));
    }, [post.likes, currentUser.uid]);

    useEffect(() => {
        if (showComments) {
            const q = query(collection(db, `/artifacts/${appId}/public/data/posts/${post.id}/comments`), orderBy('timestamp', 'asc'));
            const unsubscribe = onSnapshot(q, (snapshot) => {
                setComments(snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() })));
            });
            return () => unsubscribe();
        }
    }, [showComments, post.id]);

    const handleLike = () => {
        api.toggleLike(post.id, currentUser.uid);
    };

    const handleCommentSubmit = async (e) => {
        e.preventDefault();
        if (newComment.trim()) {
            await api.addComment(post.id, currentUser, newComment);
            setNewComment('');
        }
    };
    
    const timeAgo = (timestamp) => {
        if (!timestamp) return '';
        const now = new Date();
        const postDate = timestamp.toDate();
        const seconds = Math.floor((now - postDate) / 1000);
        let interval = seconds / 31536000;
        if (interval > 1) return Math.floor(interval) + "y";
        interval = seconds / 2592000;
        if (interval > 1) return Math.floor(interval) + "m";
        interval = seconds / 86400;
        if (interval > 1) return Math.floor(interval) + "d";
        interval = seconds / 3600;
        if (interval > 1) return Math.floor(interval) + "h";
        interval = seconds / 60;
        if (interval > 1) return Math.floor(interval) + "m";
        return Math.floor(seconds) + "s";
    }

    const goToProfile = (userId) => {
        navigate('profile', { user: { uid: userId } });
    };

    return (
        <div className="p-4 border-b border-gray-700 hover:bg-gray-800/50 transition-colors duration-200">
            <div className="flex space-x-4">
                <img src={post.authorPhotoURL} alt={post.authorName} className="h-12 w-12 rounded-full cursor-pointer" onClick={() => goToProfile(post.authorId)} />
                <div className="flex-1">
                    <div className="flex items-center space-x-2">
                        <span className="font-bold cursor-pointer" onClick={() => goToProfile(post.authorId)}>{post.authorName}</span>
                        <span className="text-gray-500 text-sm">· {timeAgo(post.timestamp)}</span>
                    </div>
                    <p className="mt-1 whitespace-pre-wrap">{post.text}</p>
                    {post.imageUrls && post.imageUrls.length > 0 && (
                        <div className={`mt-3 grid gap-2 ${post.imageUrls.length > 1 ? 'grid-cols-2' : 'grid-cols-1'}`}>
                            {post.imageUrls.map((url, index) => (
                                <img key={index} src={url} alt="Post content" className="rounded-lg w-full h-auto object-cover border border-gray-700" />
                            ))}
                        </div>
                    )}
                    <div className="flex justify-between mt-4 text-gray-500 max-w-xs">
                        <button onClick={() => setShowComments(!showComments)} className="flex items-center space-x-2 hover:text-blue-500">
                            <MessageCircle size={20} />
                            <span>{post.commentsCount || 0}</span>
                        </button>
                        <button onClick={handleLike} className={`flex items-center space-x-2 ${isLiked ? 'text-red-500' : 'hover:text-red-500'}`}>
                            <Heart size={20} fill={isLiked ? 'currentColor' : 'none'} />
                            <span>{post.likes.length}</span>
                        </button>
                        <button className="flex items-center space-x-2 hover:text-green-500" onClick={() => alert(t('under_development'))}>
                            <Repeat size={20} />
                            <span>{post.repostsCount || 0}</span>
                        </button>
                    </div>
                </div>
            </div>
            {showComments && (
                <div className="mt-4 pl-16">
                    <form onSubmit={handleCommentSubmit} className="flex space-x-2 mb-4">
                        <input
                            type="text"
                            value={newComment}
                            onChange={(e) => setNewComment(e.target.value)}
                            placeholder={t('add_comment')}
                            className="flex-1 bg-gray-800 border border-gray-600 rounded-full px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
                        />
                        <button type="submit" className="bg-blue-600 text-white px-4 py-2 rounded-full font-semibold">{t('post_comment')}</button>
                    </form>
                    <div className="space-y-4">
                        {comments.map(comment => (
                            <div key={comment.id} className="flex space-x-3">
                                <img src={comment.authorPhotoURL} alt={comment.authorName} className="h-8 w-8 rounded-full cursor-pointer" onClick={() => goToProfile(comment.authorId)} />
                                <div className="bg-gray-800 rounded-lg p-2 flex-1">
                                    <span className="font-bold text-sm cursor-pointer" onClick={() => goToProfile(comment.authorId)}>{comment.authorName}</span>
                                    <p className="text-sm">{comment.text}</p>
                                </div>
                            </div>
                        ))}
                    </div>
                </div>
            )}
        </div>
    );
};

const Feed = ({ user }) => {
    const [posts, setPosts] = useState([]);
    const [loading, setLoading] = useState(true);
    const { t } = useTranslation();

    useEffect(() => {
        const q = query(collection(db, `/artifacts/${appId}/public/data/posts`), orderBy('timestamp', 'desc'));
        const unsubscribe = onSnapshot(q, (snapshot) => {
            setPosts(snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() })));
            setLoading(false);
        }, (error) => {
            console.error("Error fetching posts:", error);
            setLoading(false);
        });
        return () => unsubscribe();
    }, []);

    if (loading) {
        return <div className="flex justify-center items-center h-screen"><Spinner /></div>;
    }

    return (
        <div>
            <h1 className="text-xl font-bold p-4 border-b border-gray-700">{t('feed_title')}</h1>
            <PostForm user={user} onPost={() => {}} />
            <div>
                {posts.map(post => (
                    <Post key={post.id} post={post} currentUser={user} />
                ))}
            </div>
        </div>
    );
};

const NotificationsPage = ({ user }) => {
    const [notifications, setNotifications] = useState([]);
    const [loading, setLoading] = useState(true);
    const { t } = useTranslation();
    const { navigate } = useNavigation();

    useEffect(() => {
        const q = query(collection(db, `/artifacts/${appId}/users/${user.uid}/notifications`), orderBy('timestamp', 'desc'));
        const unsubscribe = onSnapshot(q, (snapshot) => {
            setNotifications(snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() })));
            setLoading(false);
        });
        return () => unsubscribe();
    }, [user.uid]);

    const getNotificationMessage = (notification) => {
        switch (notification.type) {
            case 'like': return t('new_like');
            case 'comment': return t('new_comment');
            case 'follow': return t('new_follow');
            default: return '';
        }
    };
    
    const handleNotificationClick = (notif) => {
        if (notif.type === 'follow') {
            navigate('profile', { user: { uid: notif.fromUserId } });
        }
        // Could add navigation to specific post for like/comment
    };

    if (loading) {
        return <div className="flex justify-center items-center h-screen"><Spinner /></div>;
    }

    return (
        <div>
            <h1 className="text-xl font-bold p-4 border-b border-gray-700">{t('notifications')}</h1>
            {notifications.length === 0 ? (
                <p className="text-gray-500 text-center p-8">{t('no_notifications')}</p>
            ) : (
                notifications.map(notif => (
                    <div key={notif.id} onClick={() => handleNotificationClick(notif)} className="p-4 border-b border-gray-700 flex items-center space-x-4 cursor-pointer hover:bg-gray-800/50">
                        {notif.type === 'like' && <Heart className="text-red-500" />}
                        {notif.type === 'comment' && <MessageCircle className="text-blue-500" />}
                        {notif.type === 'follow' && <User className="text-green-500" />}
                        <img src={notif.fromUserPhotoURL} alt={notif.fromUserName} className="h-10 w-10 rounded-full" />
                        <div>
                            <span className="font-bold">{notif.fromUserName}</span>
                            <span className="ml-1">{getNotificationMessage(notif)}</span>
                        </div>
                    </div>
                ))
            )}
        </div>
    );
};

const ProfilePage = ({ profileUser, currentUser }) => {
    const [userData, setUserData] = useState(null);
    const [userPosts, setUserPosts] = useState([]);
    const [loading, setLoading] = useState(true);
    const { t } = useTranslation();

    useEffect(() => {
        const fetchUserData = async () => {
            setLoading(true);
            const fetchedUser = await api.getUser(profileUser.uid);
            setUserData(fetchedUser);

            const q = query(collection(db, `/artifacts/${appId}/public/data/posts`), where('authorId', '==', profileUser.uid), orderBy('timestamp', 'desc'));
            const postsSnapshot = await getDocs(q);
            setUserPosts(postsSnapshot.docs.map(doc => ({ id: doc.id, ...doc.data() })));

            setLoading(false);
        };
        fetchUserData();
    }, [profileUser.uid]);

    const handleFollowToggle = async () => {
        await api.toggleFollow(currentUser, userData.id);
    };

    if (loading || !userData) {
        return <div className="flex justify-center items-center h-screen"><Spinner /></div>;
    }
    
    const isFollowing = currentUser.following?.includes(userData.id);

    return (
        <div>
            <div className="border-b border-gray-700">
                <div className="relative h-48 bg-gray-700">
                    {/* Banner Image */}
                </div>
                <div className="p-4">
                    <div className="flex justify-between items-start">
                        <img src={userData.photoURL} alt={userData.displayName} className="h-32 w-32 rounded-full -mt-20 border-4 border-gray-900" />
                        {currentUser.uid === userData.id ? (
                            <button className="border border-gray-500 text-white font-bold py-2 px-4 rounded-full">{t('edit_profile')}</button>
                        ) : (
                            <button onClick={handleFollowToggle} className={`${isFollowing ? 'bg-transparent border border-white text-white' : 'bg-white text-black'} font-bold py-2 px-4 rounded-full transition-colors`}>
                                {isFollowing ? t('following') : t('follow')}
                            </button>
                        )}
                    </div>
                    <h1 className="text-xl font-bold mt-2">{userData.displayName}</h1>
                    <div className="flex space-x-6 text-gray-400 mt-2">
                        <span><span className="font-bold text-white">{userData.following.length}</span> {t('following')}</span>
                        <span><span className="font-bold text-white">{userData.followers.length}</span> {t('followers')}</span>
                    </div>
                </div>
            </div>
            <h2 className="text-lg font-bold p-4 border-b border-gray-700">{t('posts')}</h2>
            <div>
                {userPosts.map(post => (
                    <Post key={post.id} post={post} currentUser={currentUser} />
                ))}
            </div>
        </div>
    );
};

const SearchPage = ({ currentUser }) => {
    const [searchTerm, setSearchTerm] = useState('');
    const [results, setResults] = useState([]);
    const [loading, setLoading] = useState(false);
    const { t } = useTranslation();
    const { navigate } = useNavigation();

    useEffect(() => {
        const performSearch = async () => {
            if (searchTerm.trim() === '') {
                setResults([]);
                return;
            }
            setLoading(true);
            const users = await api.searchUsers(searchTerm);
            setResults(users.filter(u => u.id !== currentUser.uid));
            setLoading(false);
        };
        const debounce = setTimeout(() => {
            performSearch();
        }, 300); // Debounce search to avoid too many requests
        return () => clearTimeout(debounce);
    }, [searchTerm, currentUser.uid]);

    return (
        <div>
            <div className="p-4 border-b border-gray-700 sticky top-0 bg-gray-900/80 backdrop-blur-md">
                <input
                    type="text"
                    value={searchTerm}
                    onChange={(e) => setSearchTerm(e.target.value)}
                    placeholder={t('search_users')}
                    className="w-full bg-gray-800 border border-gray-700 rounded-full px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
                />
            </div>
            {loading && <div className="p-4 flex justify-center"><Spinner /></div>}
            {!loading && results.length === 0 && searchTerm && (
                 <p className="text-gray-500 text-center p-8">{t('no_users_found')}</p>
            )}
            <div>
                {results.map(user => (
                    <div key={user.id} onClick={() => navigate('profile', { user: { uid: user.id } })} className="p-4 border-b border-gray-700 flex items-center space-x-4 cursor-pointer hover:bg-gray-800/50">
                        <img src={user.photoURL} alt={user.displayName} className="h-12 w-12 rounded-full" />
                        <div>
                            <p className="font-bold">{user.displayName}</p>
                            <p className="text-gray-500 text-sm">@{user.displayName.toLowerCase().replace(/\s/g, '')}</p>
                        </div>
                    </div>
                ))}
            </div>
        </div>
    );
};

const WhoToFollow = ({ currentUser }) => {
    const [users, setUsers] = useState([]);
    const { t } = useTranslation();
    const { navigate } = useNavigation();

    useEffect(() => {
        const fetchUsers = async () => {
            const usersRef = collection(db, `/artifacts/${appId}/public/data/users`);
            const q = query(usersRef, limit(10));
            const unsubscribe = onSnapshot(q, (snapshot) => {
                const allUsers = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                // Filter out the current user and users they are already following
                const suggestions = allUsers.filter(u => u.id !== currentUser.uid && !currentUser.following?.includes(u.id)).slice(0, 3);
                setUsers(suggestions);
            });
            return () => unsubscribe();
        };
        fetchUsers();
    }, [currentUser]);

    return (
        <div className="bg-gray-800 p-4 rounded-lg">
            <h2 className="font-bold text-lg mb-4">{t('who_to_follow')}</h2>
            <div className="space-y-4">
                {users.map(user => (
                    <div key={user.id} className="flex items-center justify-between">
                        <div className="flex items-center space-x-3 cursor-pointer" onClick={() => navigate('profile', { user: { uid: user.id } })}>
                            <img src={user.photoURL} alt={user.displayName} className="h-10 w-10 rounded-full" />
                            <div>
                                <p className="font-bold text-sm">{user.displayName}</p>
                                <p className="text-gray-500 text-xs">@{user.displayName.toLowerCase().replace(/\s/g, '')}</p>
                            </div>
                        </div>
                        <button onClick={() => api.toggleFollow(currentUser, user.id)} className="bg-white text-black font-bold text-sm py-1 px-3 rounded-full">
                            {t('follow')}
                        </button>
                    </div>
                ))}
            </div>
        </div>
    );
};


const LanguageSwitcher = () => {
    const { setLanguage, language } = useTranslation();
    const [isOpen, setIsOpen] = useState(false);
    const languages = { en: 'English', zh: '中文', ja: '日本語' };

    return (
        <div className="relative">
            <button onClick={() => setIsOpen(!isOpen)} className="flex items-center space-x-2 p-3 text-xl rounded-full hover:bg-gray-800 w-full text-left">
                <Globe />
                <span className="hidden lg:inline">{languages[language]}</span>
            </button>
            {isOpen && (
                <div className="absolute bottom-full mb-2 w-48 bg-gray-800 rounded-lg shadow-lg border border-gray-700 z-10">
                    {Object.entries(languages).map(([code, name]) => (
                        <button
                            key={code}
                            onClick={() => { setLanguage(code); setIsOpen(false); }}
                            className={`block w-full text-left px-4 py-2 ${language === code ? 'font-bold text-blue-400' : 'hover:bg-gray-700'}`}
                        >
                            {name}
                        </button>
                    ))}
                </div>
            )}
        </div>
    );
};

const Sidebar = ({ user }) => {
    const { t } = useTranslation();
    const { navigate, page } = useNavigation();
    
    const navItems = [
        { id: 'home', icon: Home, label: t('home') },
        { id: 'search', icon: Search, label: t('search') },
        { id: 'notifications', icon: Bell, label: t('notifications') },
        { id: 'profile', icon: User, label: t('profile') },
    ];

    const handleNavigate = (id) => {
        if (id === 'profile') {
            navigate('profile', { user: { uid: user.uid } });
        } else {
            navigate(id);
        }
    };

    return (
        <div className="h-screen flex flex-col justify-between p-2 lg:p-4 border-r border-gray-700">
            <div>
                <div className="text-blue-500 p-3">
                    <svg viewBox="0 0 24 24" aria-hidden="true" className="h-8 w-8 fill-current"><g><path d="M23.643 4.937c-.835.37-1.732.62-2.675.733.962-.576 1.7-1.49 2.048-2.578-.9.534-1.897.922-2.958 1.13-.85-.904-2.06-1.47-3.4-1.47-2.572 0-4.658 2.086-4.658 4.66 0 .364.042.718.12 1.06-3.873-.195-7.304-2.05-9.602-4.868-.4.69-.63 1.49-.63 2.342 0 1.616.823 3.043 2.072 3.878-.764-.025-1.482-.234-2.11-.583v.06c0 2.257 1.605 4.14 3.737 4.568-.39.106-.803.163-1.227.163-.3 0-.593-.028-.877-.082.593 1.85 2.313 3.198 4.352 3.234-1.595 1.25-3.604 1.995-5.786 1.995-.376 0-.747-.022-1.112-.065 2.062 1.323 4.51 2.093 7.14 2.093 8.57 0 13.255-7.098 13.255-13.254 0-.2-.005-.402-.014-.602.91-.658 1.7-1.477 2.323-2.41z"></path></g></svg>
                </div>
                <nav className="mt-5">
                    {navItems.map(item => (
                        <button key={item.id} onClick={() => handleNavigate(item.id)} className={`flex items-center space-x-4 p-3 text-xl rounded-full w-full text-left transition-colors duration-200 ${page === item.id ? 'font-bold' : 'hover:bg-gray-800'}`}>
                            <item.icon />
                            <span className="hidden lg:inline">{item.label}</span>
                        </button>
                    ))}
                </nav>
                <button className="mt-5 w-full bg-blue-600 text-white font-bold py-3 px-6 rounded-full text-center hidden lg:block hover:bg-blue-700 transition">
                    {t('post')}
                </button>
                 <button className="mt-5 lg:hidden bg-blue-600 text-white font-bold p-3 rounded-full">
                    <PlusCircle />
                </button>
            </div>
            <div className="space-y-4">
                <LanguageSwitcher />
                <button onClick={() => signOut(auth)} className="flex items-center space-x-4 p-3 text-xl rounded-full hover:bg-gray-800 w-full text-left">
                    <LogOut />
                    <span className="hidden lg:inline">{t('logout')}</span>
                </button>
            </div>
        </div>
    );
};

const MainApp = ({ user }) => {
    const { page, profileUser } = useNavigation();
    
    const renderPage = () => {
        switch (page) {
            case 'home':
                return <Feed user={user} />;
            case 'search':
                return <SearchPage currentUser={user} />;
            case 'notifications':
                return <NotificationsPage user={user} />;
            case 'profile':
                return <ProfilePage profileUser={profileUser} currentUser={user} />;
            default:
                return <Feed user={user} />;
        }
    };

    return (
        <div className="bg-gray-900 text-white min-h-screen">
            <div className="container mx-auto flex">
                <div className="w-16 lg:w-1/4 sticky top-0 h-screen">
                    <Sidebar user={user} />
                </div>
                <main className="w-full lg:w-1/2 border-l border-r border-gray-700">
                    {renderPage()}
                </main>
                <aside className="hidden lg:block w-1/4 p-4">
                    <div className="space-y-4">
                       <WhoToFollow currentUser={user} />
                    </div>
                </aside>
            </div>
        </div>
    );
};


export default function App() {
    const { user, loading } = useAuth();

    if (loading) {
        return (
            <div className="bg-gray-900 min-h-screen flex items-center justify-center">
                <Spinner />
            </div>
        );
    }

    return (
        <LanguageProvider>
            <NavigationProvider>
                {user && user.email ? <MainApp user={user} /> : <AuthPage />}
            </NavigationProvider>
        </LanguageProvider>
    );
}

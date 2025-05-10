<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موقع نشر المواقع</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary-gradient: linear-gradient(135deg, #13547a, #80d0c7);
            --primary-hover-gradient: linear-gradient(135deg, #0f4560, #6ab9b0);
            --primary-color: #13547a;
            --secondary-color: #80d0c7;
            --light-bg: #f8f9fa;
            --dark-text: #343a40;
            --medium-text: #495057;
            --light-text: #6c757d;
            --link-color: #0366d6;
            --border-color: #e9ecef;
            --card-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
            --card-hover-shadow: 0 5px 15px rgba(0, 0, 0, 0.15);
            --container-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --input-border: #ced4da;
            --success-color: #28a745;
            --danger-color: #dc3545;
            --warning-color: #ffc107;
            --info-color: #17a2b8;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa, #c3cfe2);
            min-height: 100vh;
            padding: 20px;
            transition: background 0.3s;
        }
        
        body.dark-mode {
            background: linear-gradient(135deg, #232526, #414345);
            color: #f8f9fa;
        }
        
        .dark-mode .container {
            background-color: #2d3436;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .dark-mode header {
            background: linear-gradient(135deg, #0f2027, #203a43);
        }
        
        .dark-mode .input-section,
        .dark-mode .website-header,
        .dark-mode footer,
        .dark-mode .category-tabs {
            background-color: #1e272e;
            border-color: #343a40;
        }
        
        .dark-mode .website-card {
            background-color: #2d3436;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
        }
        
        .dark-mode .website-title {
            color: #f8f9fa;
        }
        
        .dark-mode .website-desc {
            color: #adb5bd;
        }
        
        .dark-mode .website-url {
            color: #00b7ff;
        }
        
        .dark-mode .input-field {
            background-color: #2d3436;
            border-color: #495057;
            color: #f8f9fa;
        }
        
        .dark-mode .visit-btn {
            background: linear-gradient(135deg, #0f2027, #203a43);
        }
        
        .dark-mode .visit-btn:hover {
            background: linear-gradient(135deg, #12272e, #264a56);
        }
        
        .dark-mode h2, 
        .dark-mode h3, 
        .dark-mode label {
            color: #f8f9fa;
        }
        
        .dark-mode .search-container input {
            background-color: #2d3436;
            border-color: #495057;
            color: #f8f9fa;
        }
        
        .dark-mode .tab {
            background-color: #2d3436;
            color: #adb5bd;
            border-color: #495057;
        }
        
        .dark-mode .tab.active {
            background-color: #3d4d5a;
            color: #f8f9fa;
            border-bottom-color: var(--secondary-color);
        }
        
        .dark-mode .modal-content {
            background-color: #2d3436;
            color: #f8f9fa;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: var(--container-shadow);
            overflow: hidden;
            transition: all 0.3s;
        }
        
        header {
            background: var(--primary-gradient);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
        }
        
        .theme-switch {
            position: absolute;
            top: 20px;
            left: 20px;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            transition: all 0.3s;
        }
        
        .theme-switch:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        
        h1 {
            margin-bottom: 10px;
            font-size: 2.2rem;
        }
        
        .subheader {
            opacity: 0.8;
            font-size: 1rem;
            margin-bottom: 10px;
        }
        
        .input-section {
            padding: 20px;
            background-color: var(--light-bg);
            border-bottom: 1px solid var(--border-color);
            transition: all 0.3s;
        }
        
        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        .form-group, 
        .form-group-full {
            margin-bottom: 15px;
        }
        
        .form-group-full {
            grid-column: span 2;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            color: var(--dark-text);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .input-group {
            display: flex;
            margin-bottom: 15px;
        }
        
        .input-field {
            flex: 1;
            padding: 12px 15px;
            font-size: 16px;
            border: 1px solid var(--input-border);
            border-radius: 5px;
            outline: none;
            transition: all 0.3s;
        }
        
        .input-field:focus {
            border-color: var(--secondary-color);
            box-shadow: 0 0 0 2px rgba(128, 208, 199, 0.25);
        }
        
        .add-btn {
            background: var(--primary-gradient);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        
        .add-btn:hover {
            background: var(--primary-hover-gradient);
            transform: translateY(-2px);
        }
        
        .category-tabs {
            display: flex;
            background-color: var(--light-bg);
            border-bottom: 1px solid var(--border-color);
            overflow-x: auto;
            padding: 0 10px;
            transition: all 0.3s;
        }
        
        .tab {
            padding: 15px 20px;
            cursor: pointer;
            transition: all 0.3s;
            white-space: nowrap;
            border-bottom: 3px solid transparent;
            color: var(--light-text);
            font-weight: 500;
        }
        
        .tab:hover {
            color: var(--dark-text);
            background-color: rgba(0, 0, 0, 0.03);
        }
        
        .tab.active {
            color: var(--primary-color);
            border-bottom-color: var(--secondary-color);
            font-weight: 600;
        }
        
        .search-container {
            padding: 15px 20px;
            background-color: var(--light-bg);
            border-bottom: 1px solid var(--border-color);
            display: flex;
            align-items: center;
            transition: all 0.3s;
        }
        
        .search-container input {
            flex: 1;
            padding: 10px 15px;
            border: 1px solid var(--input-border);
            border-radius: 5px;
            font-size: 16px;
            transition: all 0.3s;
        }
        
        .search-container input:focus {
            border-color: var(--secondary-color);
            outline: none;
            box-shadow: 0 0 0 2px rgba(128, 208, 199, 0.25);
        }
        
        .websites-section {
            padding: 20px;
        }
        
        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .section-title {
            font-size: 1.5rem;
            color: var(--dark-text);
            transition: color 0.3s;
        }
        
        .view-toggle {
            display: flex;
            border: 1px solid var(--border-color);
            border-radius: 5px;
            overflow: hidden;
        }
        
        .view-toggle button {
            background: none;
            border: none;
            padding: 8px 12px;
            cursor: pointer;
            transition: all 0.3s;
            color: var(--light-text);
        }
        
        .view-toggle button.active {
            background-color: var(--primary-color);
            color: white;
        }
        
        .websites-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            transition: all 0.3s;
        }
        
        .websites-container.list-view {
            grid-template-columns: 1fr;
        }
        
        .websites-container.list-view .website-card {
            display: flex;
            flex-direction: row;
        }
        
        .websites-container.list-view .website-header {
            width: 200px;
            border-bottom: none;
            border-right: 1px solid var(--border-color);
        }
        
        .websites-container.list-view .website-body {
            flex: 1;
        }
        
        .website-card {
            background-color: #fff;
            border-radius: 5px;
            box-shadow: var(--card-shadow);
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .website-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--card-hover-shadow);
        }
        
        .website-header {
            background-color: var(--light-bg);
            padding: 15px;
            border-bottom: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
        }
        
        .website-title {
            font-weight: 600;
            font-size: 18px;
            color: var(--dark-text);
            transition: color 0.3s;
        }
        
        .website-actions {
            display: flex;
        }
        
        .website-actions button {
            background: none;
            border: none;
            cursor: pointer;
            color: var(--light-text);
            font-size: 20px;
            transition: color 0.3s;
            margin-right: 5px;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .website-actions button:hover {
            color: var(--dark-text);
            background-color: rgba(0, 0, 0, 0.05);
        }
        
        .website-body {
            padding: 15px;
        }
        
        .website-meta {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 12px;
            color: var(--light-text);
        }
        
        .website-category {
            background-color: rgba(128, 208, 199, 0.2);
            color: var(--primary-color);
            padding: 3px 8px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 500;
        }
        
        .website-url {
            color: var(--link-color);
            margin-bottom: 8px;
            word-break: break-all;
            transition: color 0.3s;
        }
        
        .website-desc {
            color: var(--medium-text);
            font-size: 14px;
            margin-bottom: 15px;
            line-height: 1.5;
            transition: color 0.3s;
        }
        
        .website-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .visit-btn {
            display: inline-block;
            background: var(--primary-gradient);
            color: white;
            padding: 8px 15px;
            border-radius: 4px;
            text-decoration: none;
            font-size: 14px;
            transition: all 0.3s ease;
        }
        
        .visit-btn:hover {
            background: var(--primary-hover-gradient);
            transform: translateY(-2px);
        }
        
        .website-stats {
            display: flex;
            align-items: center;
        }
        
        .stat {
            display: flex;
            align-items: center;
            margin-right: 10px;
            color: var(--light-text);
            font-size: 14px;
        }
        
        .stat i {
            margin-right: 4px;
        }
        
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            color: var(--light-text);
        }
        
        .empty-icon {
            font-size: 80px;
            margin-bottom: 15px;
            opacity: 0.5;
        }
        
        .empty-title {
            font-size: 24px;
            margin-bottom: 10px;
            color: var(--medium-text);
        }
        
        .empty-desc {
            font-size: 16px;
            max-width: 500px;
            margin: 0 auto 20px;
        }
        
        .empty-state .add-btn {
            margin-top: 10px;
        }
        
        footer {
            background-color: var(--light-bg);
            padding: 20px;
            text-align: center;
            color: var(--light-text);
            border-top: 1px solid var(--border-color);
            transition: all 0.3s;
        }
        
        .footer-links {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: var(--primary-color);
            margin: 0 10px;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: var(--secondary-color);
            text-decoration: underline;
        }
        
        .backdrop {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }
        
        .backdrop.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal {
            width: 90%;
            max-width: 500px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            transform: scale(0.8);
            transition: all 0.3s;
        }
        
        .backdrop.active .modal {
            transform: scale(1);
        }
        
        .modal-header {
            padding: 15px 20px;
            border-bottom: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .modal-title {
            font-size: 20px;
            font-weight: 600;
        }
        
        .close-modal {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--light-text);
            transition: color 0.3s;
        }
        
        .close-modal:hover {
            color: var(--danger-color);
        }
        
        .modal-body {
            padding: 20px;
        }
        
        .modal-footer {
            padding: 15px 20px;
            border-top: 1px solid var(--border-color);
            text-align: right;
        }
        
        .btn {
            padding: 8px 15px;
            border-radius: 4px;
            border: none;
            cursor: pointer;
            font-size: 14px;
            font-weight: 500;
            transition: all 0.3s;
            margin-left: 10px;
        }
        
        .btn-primary {
            background: var(--primary-gradient);
            color: white;
        }
        
        .btn-primary:hover {
            background: var(--primary-hover-gradient);
        }
        
        .btn-secondary {
            background-color: #e9ecef;
            color: var(--dark-text);
        }
        
        .btn-secondary:hover {
            background-color: #dee2e6;
        }
        
        .btn-danger {
            background-color: var(--danger-color);
            color: white;
        }
        
        .btn-danger:hover {
            background-color: #c82333;
        }
        
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            max-width: 350px;
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
            padding: 15px 20px;
            display: flex;
            align-items: center;
            transform: translateX(400px);
            transition: transform 0.3s;
            z-index: 1001;
        }
        
        .notification.active {
            transform: translateX(0);
        }
        
        .notification-icon {
            margin-right: 15px;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            flex-shrink: 0;
        }
        
        .notification-success .notification-icon {
            background-color: var(--success-color);
        }
        
        .notification-error .notification-icon {
            background-color: var(--danger-color);
        }
        
        .notification-warning .notification-icon {
            background-color: var(--warning-color);
        }
        
        .notification-info .notification-icon {
            background-color: var(--info-color);
        }
        
        .notification-content {
            flex: 1;
        }
        
        .notification-title {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .notification-message {
            font-size: 14px;
            color: var(--medium-text);
        }
        
        .pagination {
            display: flex;
            justify-content: center;
            margin-top: 30px;
        }
        
        .pagination-item {
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 5px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 500;
        }
        
        .pagination-item:hover {
            background-color: rgba(128, 208, 199, 0.1);
            color: var(--primary-color);
        }
        
        .pagination-item.active {
            background-color: var(--primary-color);
            color: white;
        }
        
        .import-export {
            margin-top: 20px;
            padding: 20px;
            background-color: var(--light-bg);
            border-radius: 5px;
            text-align: center;
        }
        
        .import-export h3 {
            margin-bottom: 15px;
            color: var(--dark-text);
        }
        
        .import-export p {
            margin-bottom: 15px;
            color: var(--medium-text);
        }
        
        @media (max-width: 768px) {
            .form-grid {
                grid-template-columns: 1fr;
            }
            
            .form-group-full {
                grid-column: auto;
            }
            
            .websites-container {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .websites-container.list-view .website-card {
                flex-direction: column;
            }
            
            .websites-container.list-view .website-header {
                width: 100%;
                border-right: none;
                border-bottom: 1px solid var(--border-color);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <button class="theme-switch" id="themeSwitch">🌙</button>
            <h1>موقع نشر المواقع</h1>
            <div class="subheader">أضف مواقعك المفضلة وشاركها مع الآخرين</div>
        </header>
        
        <div class="input-section" id="addWebsiteForm">
            <h2 style="margin-bottom: 20px;">إضافة موقع جديد</h2>
            <div class="form-grid">
                <div class="form-group">
                    <label for="websiteTitle">عنوان الموقع*</label>
                    <input type="text" id="websiteTitle" class="input-field" placeholder="عنوان الموقع" required>
                </div>
                <div class="form-group">
                    <label for="websiteUrl">رابط الموقع (URL)*</label>
                    <input type="text" id="websiteUrl" class="input-field" placeholder="https://example.com" required>
                </div>
                <div class="form-group">
                    <label for="websiteCategory">التصنيف</label>
                    <select id="websiteCategory" class="input-field">
                        <option value="عام">عام</option>
                        <option value="تعليم">تعليم</option>
                        <option value="أخبار">أخبار</option>
                        <option value="تقنية">تقنية</option>
                        <option value="ترفيه">ترفيه</option>
                        <option value="رياضة">رياضة</option>
                        <option value="تسوق">تسوق</option>
                        <option value="صحة">صحة</option>
                        <option value="سفر">سفر</option>
                        <option value="أخرى">أخرى</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="websiteRating">التقييم</label>
                    <select id="websiteRating" class="input-field">
                        <option value="5">⭐⭐⭐⭐⭐ (ممتاز)</option>
                        <option value="4">⭐⭐⭐⭐ (جيد جداً)</option>
                        <option value="3">⭐⭐⭐ (جيد)</option>
                        <option value="2">⭐⭐ (متوسط)</option>
                        <option value="1">⭐ (ضعيف)</option>
                    </select>
                </div>
                <div class="form-group-full">
                    <label for="websiteDesc">وصف الموقع</label>
                    <textarea id="websiteDesc" class="input-field" placeholder="أضف وصفاً مختصراً للموقع" rows="3"></textarea>
                </div>
                <div class="form-group-full" style="text-align: left;">
                    <button class="add-btn" id="addWebsiteBtn">إضافة الموقع</button>
                </div>
            </div>
        </div>
        
        <div class="category-tabs" id="categoryTabs">
            <div class="tab active" data-category="all">جميع المواقع</div>
            <div class="tab" data-category="تعليم">تعليم</div>
            <div class="tab" data-category="أخبار">أخبار</div>
            <div class="tab" data-category="تقنية">تقنية</div>
            <div class="tab" data-category="ترفيه">ترفيه</div>
            <div class="tab" data-category="رياضة">رياضة</div>
            <div class="tab" data-category="تسوق">تسوق</div>
            <div class="tab" data-category="صحة">صحة</div>
            <div class="tab" data-category="سفر">سفر</div>
            <div class="tab" data-category="أخرى">أخرى</div>
        </div>
        
        <div class="search-container">
            <input type="text" id="searchInput" placeholder="ابحث عن موقع...">
        </div>
        
        <div class="websites-section">
            <div class="section-header">
                <h2 class="section-title">المواقع المضافة</h2>
                <div class="view-toggle">
                    <button id="gridViewBtn" class="active">☰</button>
                    <button id="listViewBtn">☷</button>
                </div>
            </div>
            <div class="websites-container" id="websitesContainer">
                <!-- المواقع ستضاف هنا بواسطة JavaScript -->
            </div>
            <div class="pagination" id="pagination">
                <!-- الترقيم سيضاف هنا -->
            </div>
        </div>
        
        <div class="import-export">
            <h3>استيراد / تصدير المواقع</h3>
            <p>يمكنك تصدير المواقع المحفوظة أو استيراد مواقع جديدة</p>
            <button class="btn btn-primary" id="exportBtn">تصدير المواقع</button>
            <button class="btn btn-secondary" id="importBtn">استيراد المواقع</button>
        </div>
        
        <footer>
            <div class="footer-links">
                <a href="#" id="aboutLink">عن الموقع</a>
                <a href="#" id="contactLink">اتصل بنا</a>
                <a href="#" id="privacyLink">سياسة الخصوصية</a>
            </div>
            <div>&copy; 2025 موقع نشر المواقع - جميع الحقوق محفوظة</div>
        </footer>
    </div>
    
    <!-- مودال التعديل -->
    <div class="backdrop" id="editModal">
        <div class="modal">
            <div class="modal-header">
                <div class="modal-title">تعديل الموقع</div>
                <button class="close-modal" id="closeEditModal">&times;</button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label for="editTitle">عنوان الموقع*</label>
                    <input type="text" id="editTitle" class="input-field" required>
                </div>
                <div class="form-group">
                    <label for="editUrl">رابط الموقع (URL)*</label>
                    <input type="text" id="editUrl" class="input-field" required>
                </div>
                <div class="form-group<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موقع نشر المواقع</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary-gradient: linear-gradient(135deg, #13547a, #80d0c7);
            --primary-hover-gradient: linear-gradient(135deg, #0f4560, #6ab9b0);
            --primary-color: #13547a;
            --secondary-color: #80d0c7;
            --light-bg: #f8f9fa;
            --dark-text: #343a40;
            --medium-text: #495057;
            --light-text: #6c757d;
            --link-color: #0366d6;
            --border-color: #e9ecef;
            --card-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
            --card-hover-shadow: 0 5px 15px rgba(0, 0, 0, 0.15);
            --container-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --input-border: #ced4da;
            --success-color: #28a745;
            --danger-color: #dc3545;
            --warning-color: #ffc107;
            --info-color: #17a2b8;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa, #c3cfe2);
            min-height: 100vh;
            padding: 20px;
            transition: background 0.3s;
        }
        
        body.dark-mode {
            background: linear-gradient(135deg, #232526, #414345);
            color: #f8f9fa;
        }
        
        .dark-mode .container {
            background-color: #2d3436;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .dark-mode header {
            background: linear-gradient(135deg, #0f2027, #203a43);
        }
        
        .dark-mode .input-section,
        .dark-mode .website-header,
        .dark-mode footer,
        .dark-mode .category-tabs {
            background-color: #1e272e;
            border-color: #343a40;
        }
        
        .dark-mode .website-card {
            background-color: #2d3436;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
        }
        
        .dark-mode .website-title {
            color: #f8f9fa;
        }
        
        .dark-mode .website-desc {
            color: #adb5bd;
        }
        
        .dark-mode .website-url {
            color: #00b7ff;
        }
        
        .dark-mode .input-field {
            background-color: #2d3436;
            border-color: #495057;
            color: #f8f9fa;
        }
        
        .dark-mode .visit-btn {
            background: linear-gradient(135deg, #0f2027, #203a43);
        }
        
        .dark-mode .visit-btn:hover {
            background: linear-gradient(135deg, #12272e, #264a56);
        }
        
        .dark-mode h2, 
        .dark-mode h3, 
        .dark-mode label {
            color: #f8f9fa;
        }
        
        .dark-mode .search-container input {
            background-color: #2d3436;
            border-color: #495057;
            color: #f8f9fa;
        }
        
        .dark-mode .tab {
            background-color: #2d3436;
            color: #adb5bd;
            border-color: #495057;
        }
        
        .dark-mode .tab.active {
            background-color: #3d4d5a;
            color: #f8f9fa;
            border-bottom-color: var(--secondary-color);
        }
        
        .dark-mode .modal-content {
            background-color: #2d3436;
            color: #f8f9fa;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: var(--container-shadow);
            overflow: hidden;
            transition: all 0.3s;
        }
        
        header {
            background: var(--primary-gradient);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
        }
        
        .theme-switch {
            position: absolute;
            top: 20px;
            left: 20px;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            transition: all 0.3s;
        }
        
        .theme-switch:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        
        h1 {
            margin-bottom: 10px;
            font-size: 2.2rem;
        }
        
        .subheader {
            opacity: 0.8;
            font-size: 1rem;
            margin-bottom: 10px;
        }
        
        .input-section {
            padding: 20px;
            background-color: var(--light-bg);
            border-bottom: 1px solid var(--border-color);
            transition: all 0.3s;
        }
        
        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        .form-group, 
        .form-group-full {
            margin-bottom: 15px;
        }
        
        .form-group-full {
            grid-column: span 2;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            color: var(--dark-text);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .input-group {
            display: flex;
            margin-bottom: 15px;
        }
        
        .input-field {
            flex: 1;
            padding: 12px 15px;
            font-size: 16px;
            border: 1px solid var(--input-border);
            border-radius: 5px;
            outline: none;
            transition: all 0.3s;
        }
        
        .input-field:focus {
            border-color: var(--secondary-color);
            box-shadow: 0 0 0 2px rgba(128, 208, 199, 0.25);
        }
        
        .add-btn {
            background: var(--primary-gradient);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        
        .add-btn:hover {
            background: var(--primary-hover-gradient);
            transform: translateY(-2px);
        }
        
        .category-tabs {
            display: flex;
            background-color: var(--light-bg);
            border-bottom: 1px solid var(--border-color);
            overflow-x: auto;
            padding: 0 10px;
            transition: all 0.3s;
        }
        
        .tab {
            padding: 15px 20px;
            cursor: pointer;
            transition: all 0.3s;
            white-space: nowrap;
            border-bottom: 3px solid transparent;
            color: var(--light-text);
            font-weight: 500;
        }
        
        .tab:hover {
            color: var(--dark-text);
            background-color: rgba(0, 0, 0, 0.03);
        }
        
        .tab.active {
            color: var(--primary-color);
            border-bottom-color: var(--secondary-color);
            font-weight: 600;
        }
        
        .search-container {
            padding: 15px 20px;
            background-color: var(--light-bg);
            border-bottom: 1px solid var(--border-color);
            display: flex;
            align-items: center;
            transition: all 0.3s;
        }
        
        .search-container input {
            flex: 1;
            padding: 10px 15px;
            border: 1px solid var(--input-border);
            border-radius: 5px;
            font-size: 16px;
            transition: all 0.3s;
        }
        
        .search-container input:focus {
            border-color: var(--secondary-color);
            outline: none;
            box-shadow: 0 0 0 2px rgba(128, 208, 199, 0.25);
        }
        
        .websites-section {
            padding: 20px;
        }
        
        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .section-title {
            font-size: 1.5rem;
            color: var(--dark-text);
            transition: color 0.3s;
        }
        
        .view-toggle {
            display: flex;
            border: 1px solid var(--border-color);
            border-radius: 5px;
            overflow: hidden;
        }
        
        .view-toggle button {
            background: none;
            border: none;
            padding: 8px 12px;
            cursor: pointer;
            transition: all 0.3s;
            color: var(--light-text);
        }
        
        .view-toggle button.active {
            background-color: var(--primary-color);
            color: white;
        }
        
        .websites-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            transition: all 0.3s;
        }
        
        .websites-container.list-view {
            grid-template-columns: 1fr;
        }
        
        .websites-container.list-view .website-card {
            display: flex;
            flex-direction: row;
        }
        
        .websites-container.list-view .website-header {
            width: 200px;
            border-bottom: none;
            border-right: 1px solid var(--border-color);
        }
        
        .websites-container.list-view .website-body {
            flex: 1;
        }
        
        .website-card {
            background-color: #fff;
            border-radius: 5px;
            box-shadow: var(--card-shadow);
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .website-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--card-hover-shadow);
        }
        
        .website-header {
            background-color: var(--light-bg);
            padding: 15px;
            border-bottom: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
        }
        
        .website-title {
            font-weight: 600;
            font-size: 18px;
            color: var(--dark-text);
            transition: color 0.3s;
        }
        
        .website-actions {
            display: flex;
        }
        
        .website-actions button {
            background: none;
            border: none;
            cursor: pointer;
            color: var(--light-text);
            font-size: 20px;
            transition: color 0.3s;
            margin-right: 5px;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .website-actions button:hover {
            color: var(--dark-text);
            background-color: rgba(0, 0, 0, 0.05);
        }
        
        .website-body {
            padding: 15px;
        }
        
        .website-meta {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 12px;
            color: var(--light-text);
        }
        
        .website-category {
            background-color: rgba(128, 208, 199, 0.2);
            color: var(--primary-color);
            padding: 3px 8px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 500;
        }
        
        .website-url {
            color: var(--link-color);
            margin-bottom: 8px;
            word-break: break-all;
            transition: color 0.3s;
        }
        
        .website-desc {
            color: var(--medium-text);
            font-size: 14px;
            margin-bottom: 15px;
            line-height: 1.5;
            transition: color 0.3s;
        }
        
        .website-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .visit-btn {
            display: inline-block;
            background: var(--primary-gradient);
            color: white;
            padding: 8px 15px;
            border-radius: 4px;
            text-decoration: none;
            font-size: 14px;
            transition: all 0.3s ease;
        }
        
        .visit-btn:hover {
            background: var(--primary-hover-gradient);
            transform: translateY(-2px);
        }
        
        .website-stats {
            display: flex;
            align-items: center;
        }
        
        .stat {
            display: flex;
            align-items: center;
            margin-right: 10px;
            color: var(--light-text);
            font-size: 14px;
        }
        
        .stat i {
            margin-right: 4px;
        }
        
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            color: var(--light-text);
        }
        
        .empty-icon {
            font-size: 80px;
            margin-bottom: 15px;
            opacity: 0.5;
        }
        
        .empty-title {
            font-size: 24px;
            margin-bottom: 10px;
            color: var(--medium-text);
        }
        
        .empty-desc {
            font-size: 16px;
            max-width: 500px;
            margin: 0 auto 20px;
        }
        
        .empty-state .add-btn {
            margin-top: 10px;
        }
        
        footer {
            background-color: var(--light-bg);
            padding: 20px;
            text-align: center;
            color: var(--light-text);
            border-top: 1px solid var(--border-color);
            transition: all 0.3s;
        }
        
        .footer-links {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: var(--primary-color);
            margin: 0 10px;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: var(--secondary-color);
            text-decoration: underline;
        }
        
        .backdrop {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }
        
        .backdrop.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal {
            width: 90%;
            max-width: 500px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            transform: scale(0.8);
            transition: all 0.3s;
        }
        
        .backdrop.active .modal {
            transform: scale(1);
        }
        
        .modal-header {
            padding: 15px 20px;
            border-bottom: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .modal-title {
            font-size: 20px;
            font-weight: 600;
        }
        
        .close-modal {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--light-text);
            transition: color 0.3s;
        }
        
        .close-modal:hover {
            color: var(--danger-color);
        }
        
        .modal-body {
            padding: 20px;
        }
        
        .modal-footer {
            padding: 15px 20px;
            border-top: 1px solid var(--border-color);
            text-align: right;
        }
        
        .btn {
            padding: 8px 15px;
            border-radius: 4px;
            border: none;
            cursor: pointer;
            font-size: 14px;
            font-weight: 500;
            transition: all 0.3s;
            margin-left: 10px;
        }
        
        .btn-primary {
            background: var(--primary-gradient);
            color: white;
        }
        
        .btn-primary:hover {
            background: var(--primary-hover-gradient);
        }
        
        .btn-secondary {
            background-color: #e9ecef;
            color: var(--dark-text);
        }
        
        .btn-secondary:hover {
            background-color: #dee2e6;
        }
        
        .btn-danger {
            background-color: var(--danger-color);
            color: white;
        }
        
        .btn-danger:hover {
            background-color: #c82333;
        }
        
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            max-width: 350px;
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
            padding: 15px 20px;
            display: flex;
            align-items: center;
            transform: translateX(400px);
            transition: transform 0.3s;
            z-index: 1001;
        }
        
        .notification.active {
            transform: translateX(0);
        }
        
        .notification-icon {
            margin-right: 15px;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            flex-shrink: 0;
        }
        
        .notification-success .notification-icon {
            background-color: var(--success-color);
        }
        
        .notification-error .notification-icon {
            background-color: var(--danger-color);
        }
        
        .notification-warning .notification-icon {
            background-color: var(--warning-color);
        }
        
        .notification-info .notification-icon {
            background-color: var(--info-color);
        }
        
        .notification-content {
            flex: 1;
        }
        
        .notification-title {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .notification-message {
            font-size: 14px;
            color: var(--medium-text);
        }
        
        .pagination {
            display: flex;
            justify-content: center;
            margin-top: 30px;
        }
        
        .pagination-item {
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 5px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 500;
        }
        
        .pagination-item:hover {
            background-color: rgba(128, 208, 199, 0.1);
            color: var(--primary-color);
        }
        
        .pagination-item.active {
            background-color: var(--primary-color);
            color: white;
        }
        
        .import-export {
            margin-top: 20px;
            padding: 20px;
            background-color: var(--light-bg);
            border-radius: 5px;
            text-align: center;
        }
        
        .import-export h3 {
            margin-bottom: 15px;
            color: var(--dark-text);
        }
        
        .import-export p {
            margin-bottom: 15px;
            color: var(--medium-text);
        }
        
        @media (max-width: 768px) {
            .form-grid {
                grid-template-columns: 1fr;
            }
            
            .form-group-full {
                grid-column: auto;
            }
            
            .websites-container {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .websites-container.list-view .website-card {
                flex-direction: column;
            }
            
            .websites-container.list-view .website-header {
                width: 100%;
                border-right: none;
                border-bottom: 1px solid var(--border-color);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <button class="theme-switch" id="themeSwitch">🌙</button>
            <h1>موقع نشر المواقع</h1>
            <div class="subheader">أضف مواقعك المفضلة وشاركها مع الآخرين</div>
        </header>
        
        <div class="input-section" id="addWebsiteForm">
            <h2 style="margin-bottom: 20px;">إضافة موقع جديد</h2>
            <div class="form-grid">
                <div class="form-group">
                    <label for="websiteTitle">عنوان الموقع*</label>
                    <input type="text" id="websiteTitle" class="input-field" placeholder="عنوان الموقع" required>
                </div>
                <div class="form-group">
                    <label for="websiteUrl">رابط الموقع (URL)*</label>
                    <input type="text" id="websiteUrl" class="input-field" placeholder="https://example.com" required>
                </div>
                <div class="form-group">
                    <label for="websiteCategory">التصنيف</label>
                    <select id="websiteCategory" class="input-field">
                        <option value="عام">عام</option>
                        <option value="تعليم">تعليم</option>
                        <option value="أخبار">أخبار</option>
                        <option value="تقنية">تقنية</option>
                        <option value="ترفيه">ترفيه</option>
                        <option value="رياضة">رياضة</option>
                        <option value="تسوق">تسوق</option>
                        <option value="صحة">صحة</option>
                        <option value="سفر">سفر</option>
                        <option value="أخرى">أخرى</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="websiteRating">التقييم</label>
                    <select id="websiteRating" class="input-field">
                        <option value="5">⭐⭐⭐⭐⭐ (ممتاز)</option>
                        <option value="4">⭐⭐⭐⭐ (جيد جداً)</option>
                        <option value="3">⭐⭐⭐ (جيد)</option>
                        <option value="2">⭐⭐ (متوسط)</option>
                        <option value="1">⭐ (ضعيف)</option>
                    </select>
                </div>
                <div class="form-group-full">
                    <label for="websiteDesc">وصف الموقع</label>
                    <textarea id="websiteDesc" class="input-field" placeholder="أضف وصفاً مختصراً للموقع" rows="3"></textarea>
                </div>
                <div class="form-group-full" style="text-align: left;">
                    <button class="add-btn" id="addWebsiteBtn">إضافة الموقع</button>
                </div>
            </div>
        </div>
        
        <div class="category-tabs" id="categoryTabs">
            <div class="tab active" data-category="all">جميع المواقع</div>
            <div class="tab" data-category="تعليم">تعليم</div>
            <div class="tab" data-category="أخبار">أخبار</div>
            <div class="tab" data-category="تقنية">تقنية</div>
            <div class="tab" data-category="ترفيه">ترفيه</div>
            <div class="tab" data-category="رياضة">رياضة</div>
            <div class="tab" data-category="تسوق">تسوق</div>
            <div class="tab" data-category="صحة">صحة</div>
            <div class="tab" data-category="سفر">سفر</div>
            <div class="tab" data-category="أخرى">أخرى</div>
        </div>
        
        <div class="search-container">
            <input type="text" id="searchInput" placeholder="ابحث عن موقع...">
        </div>
        
        <div class="websites-section">
            <div class="section-header">
                <h2 class="section-title">المواقع المضافة</h2>
                <div class="view-toggle">
                    <button id="gridViewBtn" class="active">☰</button>
                    <button id="listViewBtn">☷</button>
                </div>
            </div>
            <div class="websites-container" id="websitesContainer">
                <!-- المواقع ستضاف هنا بواسطة JavaScript -->
            </div>
            <div class="pagination" id="pagination">
                <!-- الترقيم سيضاف هنا -->
            </div>
        </div>
        
        <div class="import-export">
            <h3>استيراد / تصدير المواقع</h3>
            <p>يمكنك تصدير المواقع المحفوظة أو استيراد مواقع جديدة</p>
            <button class="btn btn-primary" id="exportBtn">تصدير المواقع</button>
            <button class="btn btn-secondary" id="importBtn">استيراد المواقع</button>
        </div>
        
        <footer>
            <div class="footer-links">
                <a href="#" id="aboutLink">عن الموقع</a>
                <a href="#" id="contactLink">اتصل بنا</a>
                <a href="#" id="privacyLink">سياسة الخصوصية</a>
            </div>
            <div>&copy; 2025 موقع نشر المواقع - جميع الحقوق محفوظة</div>
        </footer>
    </div>
    
    <!-- مودال التعديل -->
    <div class="backdrop" id="editModal">
        <div class="modal">
            <div class="modal-header">
                <div class="modal-title">تعديل الموقع</div>
                <button class="close-modal" id="closeEditModal">&times;</button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label for="editTitle">عنوان الموقع*</label>
                    <input type="text" id="editTitle" class="input-field" required>
                </div>
                <div class="form-group">
                    <label for="editUrl">رابط الموقع (URL)*</label>
                    <input type="text" id="editUrl" class="input-field" required>
                </div>
                <div class="form-group

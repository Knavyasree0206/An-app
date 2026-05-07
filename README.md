<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Personal Journal</title>
    <!-- Google Fonts for typography -->
    <link href="https://fonts.googleapis.com/css2?family=Merriweather:wght@300;400;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <!-- Icon Library -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --primary-color: #6c5ce7;
            --primary-light: #a29bfe;
            --secondary-color: #00b894;
            --danger-color: #d63031;
            --bg-color: #f8f9fa;
            --card-bg: #ffffff;
            --text-main: #2d3436;
            --text-muted: #636e72;
            --border-color: #dfe6e9;
            --shadow-sm: 0 2px 4px rgba(0,0,0,0.05);
            --shadow-md: 0 8px 16px rgba(0,0,0,0.1);
            --radius: 12px;
            --font-display: 'Merriweather', serif;
            --font-body: 'Inter', sans-serif;
        }

        /* Dark Mode Support */
        @media (prefers-color-scheme: dark) {
            :root {
                --bg-color: #1e1e2e;
                --card-bg: #2a2a3c;
                --text-main: #ecf0f1;
                --text-muted: #b2bec3;
                --border-color: #444;
            }
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: var(--font-body);
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        /* --- Layout & Container --- */
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
            width: 100%;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border-color);
        }

        .logo {
            font-family: var(--font-display);
            font-size: 1.8rem;
            color: var(--primary-color);
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        /* --- Controls Area --- */
        .controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 25px;
        }

        .search-wrapper {
            position: relative;
            flex-grow: 1;
            max-width: 400px;
        }

        .search-wrapper i {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-muted);
        }

        .search-input {
            width: 100%;
            padding: 12px 12px 12px 40px;
            border: 1px solid var(--border-color);
            border-radius: var(--radius);
            font-family: var(--font-body);
            font-size: 0.95rem;
            background: var(--card-bg);
            color: var(--text-main);
            transition: border-color 0.2s;
        }

        .search-input:focus {
            outline: none;
            border-color: var(--primary-color);
        }

        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: var(--radius);
            font-weight: 500;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.2s ease;
            font-family: var(--font-body);
        }

        .btn-primary {
            background-color: var(--primary-color);
            color: white;
            box-shadow: 0 4px 6px rgba(108, 92, 231, 0.2);
        }

        .btn-primary:hover {
            background-color: #5649c0;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background-color: transparent;
            border: 1px solid var(--border-color);
            color: var(--text-muted);
        }

        .btn-secondary:hover {
            background-color: var(--border-color);
            color: var(--text-main);
        }

        /* --- Entry List --- */
        .entries-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20

# Chrome OS WiFi Bypass

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

Chrome OS WiFi Bypass is a simple HTML-based web application designed to bypass network restrictions on Chrome OS devices managed by administration. The entire application consists of a single HTML file with embedded JavaScript that can be served locally and accessed through a web browser.

## Repository Structure

```
.
├── README.md           # Project description and overview
├── main.html          # Complete HTML application with embedded JavaScript
└── .github/
    └── copilot-instructions.md  # This file
```

## Working Effectively

### Prerequisites
No special dependencies, build tools, or installation steps are required. The application runs directly in any modern web browser.

### Running the Application
- **ALWAYS** serve the HTML file through an HTTP server to ensure proper functionality
- **DO NOT** open main.html directly in a browser using file:// protocol as this may cause security restrictions
- Use Python's built-in HTTP server: `python3 -m http.server 8080`
- Navigate to `http://localhost:8080/main.html` in your browser
- **Timing**: Server starts instantly (< 1 second), application loads immediately

### Complete End-to-End Validation Steps
1. Navigate to repository root: `cd /path/to/Chrome-OS-WiFi-Bypass`
2. Start HTTP server: `python3 -m http.server 8080`
3. Open browser and navigate to: `http://localhost:8080/main.html`
4. **CRITICAL**: Verify the "Click Me" button is visible and functional
5. Click the button to trigger JavaScript alert with message "Button was clicked!"
6. Dismiss the alert dialog
7. **Success criteria**: Button responds to clicks and displays alert dialog correctly

### Development Workflow
- Edit `main.html` directly for any changes to functionality or styling
- **No build step required** - changes are immediately visible after browser refresh
- **No compilation, bundling, or preprocessing needed**
- Test changes by refreshing the browser page at `http://localhost:8080/main.html`

### Validation Requirements
- **ALWAYS** test the complete user interaction flow after making any changes:
  1. Serve the file with HTTP server
  2. Load the page in browser
  3. Click the button and verify alert appears
  4. Confirm no JavaScript errors in browser console
- **ALWAYS** validate that the HTML structure remains valid
- **DO NOT** skip manual testing - automated tests are not available for this simple application

## Common Tasks

### Making Code Changes
1. Edit `main.html` with any text editor or IDE
2. Save the file
3. Refresh browser page (Ctrl+F5 or Cmd+Shift+R for hard refresh)
4. Test the button functionality immediately

### Serving the Application
- **Primary method**: `python3 -m http.server 8080`
- **Alternative methods**: Any HTTP server (nginx, Apache, Node.js http-server, etc.)
- **Port**: Use any available port (8080 is recommended default)
- **Access URL**: `http://localhost:[port]/main.html`

### Troubleshooting
- **If button doesn't work**: Check browser console for JavaScript errors
- **If page doesn't load**: Ensure you're using HTTP server, not file:// protocol
- **If server won't start**: Check if port is already in use, try different port
- **Browser compatibility**: Works in all modern browsers (Chrome, Firefox, Safari, Edge)

## File Details

### main.html Analysis
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Button Example</title>
    <script>
        function handleClick() {
            alert('Button was clicked!');
        }
    </script>
</head>
<body>
    <button type="button" onclick="handleClick()">Click Me</button>
</body>
</html>
```

- **Complete self-contained application**
- **JavaScript function**: `handleClick()` triggers browser alert
- **HTML button**: Calls `handleClick()` on click event
- **No external dependencies or resources**
- **Total file size**: ~312 bytes

### README.md Content
```
# Chrome-OS-WiFi-Bypass
A simple Chrome-OS hack to bypass network restrictions. (Made for accounts managed by an administration).
```

## Development Guidelines
- **Keep it simple**: This is intentionally a minimal, single-file application
- **No frameworks**: Do not add React, Vue, jQuery, or other frameworks unless absolutely necessary
- **Browser compatibility**: Ensure code works across all major browsers
- **No external dependencies**: Keep the application self-contained in a single HTML file
- **Security**: Be mindful that this tool is intended for educational/testing purposes on managed Chrome OS devices

## Testing Strategy
- **Manual testing only**: No automated test framework is needed for this simple application  
- **Browser testing**: Test in multiple browsers when making changes
- **Functional testing**: Always verify the button click → alert workflow
- **No unit tests**: The application is too simple to warrant automated testing infrastructure

## Git Workflow
- **Direct commits to main branch** for simple changes
- **Feature branches** for significant modifications
- **No CI/CD pipeline** required for this static HTML application
- **No build artifacts** to worry about in version control

## Performance Expectations
- **Server startup**: Instant (< 1 second)
- **Page load**: Instant (< 100ms)
- **Button response**: Immediate
- **No build time**: N/A - no build process exists
- **No test time**: N/A - no automated tests exist

This application is designed to be as simple and lightweight as possible while remaining functional for its intended purpose of bypassing Chrome OS network restrictions.
# Gateway

# Gateway Browser

Gateway is a lightweight, innovative web browser designed to work seamlessly with GoNoJS, a cutting-edge web server and framework that prioritizes server-side processing and efficient data transmission. Gateway focuses on delivering a fast, secure, and streamlined browsing experience by leveraging HTML5, CSS, and advanced server-side technologies while eliminating client-side JavaScript.

## Core Features

1. **JavaScript-Free Browsing**: Gateway does not support client-side JavaScript execution, ensuring a lean and secure browsing environment.

2. **Dual Mode Operation**: 
   - Graphical Mode: Full visual rendering of web pages
   - Text Mode: Efficient, low-bandwidth browsing experience

3. **WebSocket Integration**: Native support for real-time, bidirectional communication with GoNoJS servers.

4. **Server-Sent Events (SSE) Handler**: Efficient processing of server-pushed updates for live content.

5. **Enhanced CSS Rendering**: Optimized engine for CSS animations, transitions, and layout features.

6. **Streamlined Cache Management**: Intelligent caching of pre-rendered content from GoNoJS servers.

7. **Responsive Design Support**: Native handling of CSS-based responsive layouts without JavaScript.

## Integration with Existing Browsers

To facilitate seamless integration with popular browsers like Chrome and Firefox, Gateway implements a custom URL scheme:

1. **Custom URL Scheme**: `gateway://`
   - Example: `gateway://hash=abc123`

2. **External Link Handling**:
   - When a user clicks a specially formatted link on a GoNoJS-powered website in a standard browser, it triggers the Gateway browser to open.
   - The link contains a hash that Gateway uses to retrieve the correct content from the GoNoJS server.

3. **Browser Extensions**:
   - Optional extensions for Chrome and Firefox to enhance integration.
   - Features include:
     - One-click opening of GoNoJS content in Gateway
     - Context menu options for opening links in Gateway
     - Automatic detection of GoNoJS-compatible pages

## Best Practices and Technologies

1. **Rust-based Core**: 
   - Utilize Rust for the browser's core components to ensure memory safety and high performance.
   - Leverage the `servo` project's components for web rendering.

2. **WebKit for Rendering**: 
   - Use WebKit as the rendering engine, modified to disable JavaScript execution.
   - Benefit from WebKit's efficient CSS and HTML5 processing capabilities.

3. **Protocol Implementations**:
   - Implement WebSocket support using the `tungstenite` Rust library.
   - Use `hyper` for HTTP/2 and HTTP/3 support.

4. **Security Features**:
   - Implement Content Security Policy (CSP) enforcement.
   - Utilize `ring` for cryptographic operations.
   - Implement strict HTTPS enforcement with HSTS preloading.

5. **Performance Optimizations**:
   - Implement efficient DOM caching mechanisms.
   - Use `rayon` for parallel processing of CSS and layout calculations.

6. **Cross-Platform Development**:
   - Utilize `tauri` for creating a cross-platform GUI that works on Windows, macOS, and Linux.

7. **Accessibility**:
   - Implement robust screen reader support.
   - Ensure keyboard navigation for all browser functions.

8. **Developer Tools**:
   - Create a simplified set of developer tools focused on HTML and CSS inspection, network monitoring, and performance analysis.

9. **Extension API**:
   - Develop a limited extension API that allows for content blocking and custom styling, but prohibits JavaScript injection.

10. **Data Synchronization**:
    - Implement a secure, end-to-end encrypted sync system for bookmarks and settings using `rusqlite` for local storage and a custom sync server.

By adhering to these best practices and leveraging modern technologies, Gateway aims to provide a unique, efficient, and secure browsing experience that complements the GoNoJS server-side framework, pushing the boundaries of what's possible in web browsing without client-side JavaScript.

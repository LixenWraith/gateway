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

To facilitate seamless integration with popular browsers like Chrome and Firefox, Gateway implements a custom URL scheme and browser extensions with two main purposes:

1. **Custom URL Scheme**: `gateway://`
   - Example: `gateway://hash=abc123`

2. **Browser Extensions**:
   - Optional extensions for Chrome and Firefox to enhance integration.
   - Purpose 1: Facilitate opening GoNoJS server content within the original browser
     - Render GoNoJS content directly in the existing browser when possible
     - Provide a seamless experience for users who prefer to stay in their primary browser
   - Purpose 2: No-click opening of Gateway for supported pages
     - Automatically detect embedded `gateway://` links
     - Open Gateway browser in the background when a supported page is encountered
     - Allow users to configure automatic opening behavior

3. **Extension Features**:
   - Content detection for GoNoJS-compatible pages
   - User-configurable settings for automatic Gateway launching
   - Context menu options for manually opening links in Gateway
   - Lightweight proxy for rendering GoNoJS content in the original browser when feasible

## Best Practices and Technologies

1. **Go-based Implementation**: 
   - Develop the entire browser core in Go, leveraging its strong standard library and concurrency features.
   - Utilize Go's garbage collection and memory safety features for robust performance.

2. **Rendering Engine**: 
   - Explore Go-native rendering solutions like `go-vdom` or `go-sciter` for HTML and CSS processing.
   - If necessary, create Go bindings for a lightweight C-based rendering engine like WebKit, minimizing C dependencies.

3. **Protocol Implementations**:
   - Use `gorilla/websocket` for WebSocket support.
   - Leverage `net/http` and `golang.org/x/net/http2` for HTTP/1.1 and HTTP/2 support.
   - Implement HTTP/3 support using the `quic-go` library and its HTTP/3 implementation.
   - Utilize HTTP/3 features for improved performance, especially on mobile and unreliable networks:
     - Faster connection establishment with 0-RTT
     - Better multiplexing without head-of-line blocking
     - Connection migration for seamless network switching

4. **Security Features**:
   - Implement Content Security Policy (CSP) enforcement using Go's `net/http` package.
   - Use Go's `crypto` package for cryptographic operations.
   - Implement strict HTTPS enforcement with HSTS preloading.

5. **Performance Optimizations**:
   - Implement efficient DOM caching mechanisms using Go's concurrent map implementations.
   - Utilize Go's goroutines for parallel processing of CSS and layout calculations.

6. **Cross-Platform Development**:
   - Use `fyne.io` or `gio` for creating a cross-platform GUI that works on Windows, macOS, and Linux.

7. **Accessibility**:
   - Implement robust screen reader support using OS-specific APIs via CGo when necessary.
   - Ensure keyboard navigation for all browser functions.

8. **Developer Tools**:
   - Create a simplified set of developer tools focused on HTML and CSS inspection, network monitoring, and performance analysis.

9. **Extension API**:
   - Develop a limited extension API that allows for content blocking and custom styling, but prohibits JavaScript injection.

10. **Data Synchronization**:
    - Implement a secure, end-to-end encrypted sync system for bookmarks and settings using `go-sqlite3` for local storage and a custom sync server written in Go.

By adhering to these best practices and leveraging Go's strengths, Gateway aims to provide a unique, efficient, and secure browsing experience that complements the GoNoJS server-side framework, pushing the boundaries of what's possible in web browsing without client-side JavaScript.

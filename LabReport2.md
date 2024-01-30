# Part 1
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-29%20222908.png?raw=true)
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-29%20223233.png?raw=true)
```
import java.io.IOException;
import java.net.URI;
import java.util.HashMap;
import java.util.Map;

public class ChatServer {

    static class Handler implements URLHandler {
        private StringBuilder chatHistory = new StringBuilder();

        public String handleRequest(URI url) {
            if ("/add-message".equals(url.getPath())) {
                String query = url.getQuery();
                Map<String, String> queryParams = parseQuery(query);
                String user = queryParams.get("user");
                String message = queryParams.get("s");
                chatHistory.append(user).append(": ").append(message).append("\n");
                return chatHistory.toString();
            } else {
                return "404 Not Found!";
            }
        }

        private Map<String, String> parseQuery(String query) {
            Map<String, String> queryParams = new HashMap<>();
            if (query != null && !query.isEmpty()) {
                for (String param : query.split("&")) {
                    String[] parts = param.split("=");
                    if (parts.length > 1) {
                        queryParams.put(parts[0], parts[1]);
                    } else if (parts.length == 1) {
                        queryParams.put(parts[0], "");
                    }
                }
            }
            return queryParams;
        }
    }

        public static void main(String[] args) throws IOException {
            if (args.length == 0) {
                System.out.println("Missing port number! Try any number between 1024 to 49151");
                return;
            }

            int port = Integer.parseInt(args[0]);
            Server.start(port, new Handler());
        }
    }
```
# Part 2 

# Part 3

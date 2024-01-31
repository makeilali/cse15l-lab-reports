# Part 1
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-29%20222908.png?raw=true)
- Which methods in your code are called?
  - The methods called in my code are handleRequest(URI url) and parseQuery(String query).
- What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  - The relevant aregument to handleRequest is url and the chatHistory that stores the input of the url. parseQuery helps aid handleRequest.
- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  - chatHistory is updated when the /add-message is ran with inputs.
![Image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-29%20223233.png?raw=true)
- Which methods in your code are called?
  - The methods called in my code are handleRequest(URI url) and parseQuery(String query).
- What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  - The relevant arrguments to parseQuery are query which is the input in the url.
- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  - No values got changed since this method helps aid the chatHistory and handleRequest.
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
- ssh public key
![image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-30%20at%203.21.19%20PM.png?raw=true)
- ssh private key
![image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-30%20at%203.21.27%20PM.png?raw=true)
- Terminal interaction that didn't require a password. 
![image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-30%20at%203.22.04%20PM.png?raw=true)
- Ls to show the private and plublic ssh keys.
![image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-01-30%20at%203.29.24%20PM.png?raw=true)

# Part 3
Something I learned in week 2 and 3 are the different uses of commands in a server and how they respond to inputs. ANother thing I learned was running a server through edstem and running a server through another place like vscode and was able to see the differences.

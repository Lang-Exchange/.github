<div id="top"></div>


<!-- PROJECT LOGO -->
<br />
<div align="center">
  
  <img src="https://github.com/Lang-Exchange/.github/blob/main/assets/logo.9d97ecdc029d2db586b3.png" alt="Logo" height="80">
</div>


# LangExchange - Learning language community

LangExchange is a community application that helps everyone can connect together to talk, share, study… and improve their language skill. 

## 1. About this project
It serves as a culmination of our studies, applying the knowledge and skills we acquired throughout our academic journey. By completing this thesis, we hope to contribute to the advancement of knowledge in the software engineering world while also demonstrating our ability to apply theoretical concepts to real-world scenarios. We are grateful for the guidance and support provided by our university, especially Mrs. Thu during the course of this project.

## 2. Developer team and their roles in this project
- Nguyen Van Thuong: Frontend developer.
- Nguyen Tan Xanh: Backend developer.

## 3. Features
### Innovative features:
1. Collaboratively correction: Language text on posts and personal messages (using in chatting app) can be corrected by another user in the community (such as grammar or semantic errors).
2. Pronunciation assessment chatbot: helps assess pronunciation performance in almost all kinds of language. See more in the  [chatbot repo](https://github.com/langexchange/lec-chatbot).
3. Vocabulary deck sharing: A user can creatively create a vocabulary deck which then can be shared with the community. Once the deck is shared, it can be collected by another user for further learning.
4. Vocabulary learning: Collected vocabulary decks can be learned later. The learning methodology applied is space repetition using the [Suppermemo](https://www.supermemo.com/en) algorithm, which helps the user to effectively recall a vocabulary card by predicting a suitable time at which the card should appear to recall again in the future. This can be achieved by using a formula that is implied from studying the human brain. [See more](https://en.wikipedia.org/wiki/SuperMemo).

### Common features:
#### Personal information page
1. Setting basic information: Users are required to set their target language and native language in advance to take advantage of the app's recommendation system.
2. Tracking user learning progress: Collected vocabulary decks and the dashboard which manifests the user's learning progress (vocabularies learned, collected, the completion percentage of decks collected) on those decks are displayed here.
#### Community page
1. Q&A post: The post is used to ask questions related to a particular language topic. It can be tagged (for further filtering), interacted with (determine its quality), and attached media files (image, recording audio).
2. Recommendation: It is required to define the language asked in the post. The post then will be displayed to both native speakers and language learners of the post's language.
#### Friend suggestion page
1. Tracking user's friend list.
2. Friend Exploration: Simply suggest friends who are native speakers and language learners of the user's target language. 
We are also considering an enhanced recommendation system that can suggest friends who align with users based on various factors such as hobbies, learning progress, and location, etc.
#### Chatting page
1. Basic chatting features: Such as the presence of friends (online, offline, busy), and chat state (active, inactive, composing, paused, gone). These features enhance user interaction experiences.
2. Media sharing: Images, documents, or especially audio can be shared to take advantage of collaboratively correction features by which another user can correct the user's pronunciation errors.
3. Pronunciation assessment chatbot: As mentioned above.
4. Display option: Users can use the chat feature in overlayed or fullscreen mode.
#### Other auxiliary features
1. Notifications: Basic notifications about users' actions (friends' posts, invitations) on the app, especially monthly summaries of the user learning progress informed here.
2. Dictionary: Users can use a dictionary associated with the app to search words directly whenever they encounter new words on the app.

## 4. Architecture

![image](https://github.com/Lang-Exchange/.github/blob/main/assets/architecture.png)


## 5. Tech stack
### User inrterface layer

| Service       | Type                         | Tech              |
|---------------|------------------------------|-------------------|
| API Gateway   | API Gateway                  | .Net core         |
| App Frontend  | Webserver                    | ReactJs, Nginx    |
| Chat Frontend | Webserver                    | ConverseJs, Ngixn |
| Reverse Proxy | Reverse Proxy, Load balancer | Nginx             |


### Application layer
| Service              | Type               | Tech            |
|----------------------|--------------------|-----------------|
| User service         | API Service        | C#, .Net Core   |
| Admin service        | API Service        | C#, .Net Core   |
| Uploader service     | API Service        | C#, .Net Core   |
| Notification service | API Service        | C#, .Net Core   |
| Chat service         | XMPP server        | Elang, Ejabberd |
| Chathelper service   | API Service        | Python, Django  |
| Chatbot              | Chat client        | Python, Slixmpp |
| Celery worker        | Distributed worker | Python, Celery  |

### Data layer
1. PostgreSql
1. Kafka
2. Redis
3. GraphDb

# Echorus Server Api Docs

**url : [https://echorous.herokuapp.com](https://echorous.herokuapp.com/)**

### overview

- [**https://echorous.herokuapp.com**](https://echorous.herokuapp.com/)
    - **/card**
        - /
        - /{category}
        - /search?word=””&opt=””
    - **/achievement**
        - /
        - category/{success}
        - /{id}
    - **/user**
        - /search
        - /search/{name}
        - /save
        - /achievement
    - **/auth**
        - /register
        - /login
        - /logout

# Schema
    
    Card {
    	int id
    	String image // echorous.herokuapp.com/card/image/{id}.jpg
    	String title
    	int category 
    	// ['일반' : 0,'대기' : 1,'토양': 2,'해양' : 3,'쓰레기' : 4,'우주' : 5,'방사능' : 6]
    	int style 
    	// ['환경' : 0,'경제' : 1,'민심' : 2,'재해' : 3]
    	String description
    	int soil
    	int air
    	int radio
    	int trash
    	int ocean
    	int approval
    	int capital
    	int product
    }
    
    Achievement {
    	int id
    	String name
    	int success // ['성공': 1, '실패' : 0]
    	String description
    	int count // 업적 달성한 사람의 수
    	int soil
    	int air
    	int radio
    	int trash
    	int ocean
    	int approval
    	int capital
    	int product
    	int disaster (0,1)
    	int universe (0,1)
    	int year
    }
    
    User{
    	int id
    	String username
    	int soil
    	int air
    	int radio  
    	int trash 
    	int ocean 
    	int approval 
    	int capital 
    	int product
    	int year 
    	int success
    }
    AchievementList{
    	int id
    	int user_id (foriegn key : User)
    	int achievement_id
    	String username
    }
    AuthUser{
    	int id(auto increment)
    	String login_id(unique=True)
    	String name(not null)
    	bool is_superuser(default=False)
    	bool is_staff(default=False)
    	bool is_active(default=True)
    	Datetime created_at
    	Datetime update_at
    }

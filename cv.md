# Yuliya Adamovich 

tell: +393806959384


email: ylia_adamovich@mail.ru


LinkedIn: yliaadamovich15@gmail.com


![avatar image](https://raw.githubusercontent.com/YuliAdam/rsschool-cv/gh-pages/img/IMG_5632.jpeg)


## About me 

I am 30 years old, from Belarus. I live in Italy.  I started studying programming at university like and physics and mathematics matters. It was Pascal. I acquire new skills very quickly because I have mathematical mind. I organize learning and working process very good.  
I started studying Java one year ago. I finished course "PROGRAMMAZIONE Java-M01" by Abforma. I used in my test project also Java Spring ( Spring Boot, Spring Security, Spring Data JPA, Spring MVC).  
I like books, doing long walks, travelling. I am a very positive and kind person, but also responsible and serious at work.  
I want to work in programming.

## Skills

* Java
* SQL
* MySQL
* A little HTML

## Code example 

```
@RestController
@RequestMapping("/user")
@Validated
public class UserController {
    @Autowired
    private UserService userService;
    @Autowired
    private MoneyService moneyService;

    @GetMapping("/search")
    public  ModelAndView findUsers(Model model, @RequestParam(required = false) String paramtr,
                                        @RequestParam(required = false,defaultValue = "user_name") String sort,
                                        @RequestParam(required = false, defaultValue = "0") Integer pageNumber,
                                        @RequestParam(required = false, defaultValue = "5") Integer pageSize) {
        model.addAttribute("role",SecurityContextHolder.getContext().getAuthentication().getAuthorities().toString());
        model.addAttribute("currentUserId",userService.getUserByLogin(SecurityContextHolder.getContext().getAuthentication().getName()).getId());
        model.addAttribute("moneyByCurrentUserId", moneyService.findByUserId(userService.getUserByLogin(SecurityContextHolder.getContext().getAuthentication().getName()).getId()));

        model.addAttribute("paramtr",paramtr );
        model.addAttribute("sort",sort );
        model.addAttribute("pageNumber",pageNumber );
        model.addAttribute("pageSize",pageSize );
        return new ModelAndView("users","users",userService.findUsers(paramtr, sort, pageNumber, pageSize));
    }
```


## Experience 

* cv.md for rsschool


## Education 

1) Belarus State University Physics faculty 

2) Abforma course "INGLESE-A2"

3) Abforma course "PROGRAMMAZIONE Java-M01"


## Languages 

* russian ( native)
* belarusian (native)
* english (A2)
* italian (C2)

 

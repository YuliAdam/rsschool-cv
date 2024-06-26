# Yuliya Adamovich 

tell: +393806959384


email: ylia_adamovich@mail.ru


LinkedIn: yliaadamovich15@gmail.com


## About me 

Since childhood, I studied mathematics and physics. I finished the Belarusian State University, Faculty of Physics where I started learning programming. I continued to study developing after university. Currently I’m studying Java Back-end and have also started stydy HTML, CSS and JavaScript. I am study very fast, sociable and positive person.


## Skills

* Java
* SQL
* MySQL


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
    @GetMapping("/redirect/create")
    public ModelAndView getUser(Model model) {
        model.addAttribute("user", new UserRequest());
        return new ModelAndView("addUser");
    }
    @GetMapping(value = "/{id}/redirect/update")
    public ModelAndView getUser(@PathVariable Long id, Model model) {
        model.addAttribute("role", SecurityContextHolder.getContext().getAuthentication().getAuthorities().toString());
        model.addAttribute("currentUserId",userService.getUserByLogin(SecurityContextHolder.getContext().getAuthentication().getName()).getId());
        model.addAttribute("allRoles", Role.values());
        return new ModelAndView("user", "user", userService.getUser(id));
    }

    @DeleteMapping("/{id}/delete")
    public ModelAndView deleteUser(@PathVariable Long id,Model model,
                                   @RequestParam(required = false) String paramtr,
                                   @RequestParam(required = false,defaultValue = "user_name") String sort,
                                   @RequestParam(required = false, defaultValue = "0") Integer pageNumber,
                                   @RequestParam(required = false, defaultValue = "5") Integer pageSize) {
        model.addAttribute("role",SecurityContextHolder.getContext().getAuthentication().getAuthorities().toString());
        model.addAttribute("paramtr",paramtr );
        model.addAttribute("sort",sort );
        model.addAttribute("pageNumber",pageNumber );
        model.addAttribute("pageSize",pageSize );
        userService.deleteUser(id);
        model.addAttribute("user", new UserRequest());
        model.addAttribute("moneyByCurrentUserId", moneyService.findByUserId(userService.getUserByLogin(SecurityContextHolder.getContext().getAuthentication().getName()).getId()));

        model.addAttribute("role",SecurityContextHolder.getContext().getAuthentication().getAuthorities().toString());
        model.addAttribute("currentUserId",userService.getUserByLogin(SecurityContextHolder.getContext().getAuthentication().getName()).getId());
        return new ModelAndView("users","users",userService.findUsers(paramtr, sort, pageNumber, pageSize));
    }

    @PostMapping("/create")
    public ModelAndView createUser(@ModelAttribute("user") @Valid UserRequest userRequest, Model model,
                                   @RequestParam(required = false) String paramtr,
                                   @RequestParam(required = false,defaultValue = "user_name") String sort,
                                   @RequestParam(required = false, defaultValue = "0") Integer pageNumber,
                                   @RequestParam(required = false, defaultValue = "5") Integer pageSize) {
        paramtr= userRequest.getUserName();
        model.addAttribute("paramtr",paramtr );
        model.addAttribute("sort",sort );
        model.addAttribute("pageNumber",pageNumber );
        model.addAttribute("pageSize",pageSize );
        userService.createUser(userRequest);
        model.addAttribute("user", new UserRequest());
        return new ModelAndView("/login");
    }

    @PutMapping("/update")
    public ModelAndView updateUser(@ModelAttribute("user") @Valid UserRequest userRequest,Model model,
                                   @RequestParam(required = false) String paramtr,
                                   @RequestParam(required = false,defaultValue = "user_name") String sort,
                                   @RequestParam(required = false, defaultValue = "0") Integer pageNumber,
                                   @RequestParam(required = false, defaultValue = "5") Integer pageSize) {
        paramtr= userRequest.getUserName();
        model.addAttribute("role",SecurityContextHolder.getContext().getAuthentication().getAuthorities().toString());
        model.addAttribute("paramtr",paramtr );
        model.addAttribute("sort",sort );
        model.addAttribute("pageNumber",pageNumber );
        model.addAttribute("pageSize",pageSize );
        userService.updateUser(userRequest.getId(),userRequest);
        model.addAttribute("user", new UserRequest());
        model.addAttribute("moneyByCurrentUserId", moneyService.findByUserId(userService.getUserByLogin(SecurityContextHolder.getContext().getAuthentication().getName()).getId()));

        model.addAttribute("role", SecurityContextHolder.getContext().getAuthentication().getAuthorities().toString());
        model.addAttribute("currentUserId",userService.getUserByLogin(SecurityContextHolder.getContext().getAuthentication().getName()).getId());
        model.addAttribute("allRoles", Role.values());
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

 

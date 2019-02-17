

## ToDo

* Servlet의 Life Cycle에 대해 알아보자.

---

## 프로젝트 코드

### Servlet 클래스 

``` java
public class HelloServlet extends HttpServlet {

    @Override
    public void init() throws ServletException {
        System.out.println("=====Init=====");
    }

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("=====doGet=====");
        resp.getWriter().println("<html>");
        resp.getWriter().println("<head>");
        resp.getWriter().println("<body>");
        resp.getWriter().println("<h1>Hello Servlet</h1>");
        resp.getWriter().println("</body>");
        resp.getWriter().println("</head>");
        resp.getWriter().println("</html>");
    }

    @Override
    public void destroy() {
        System.out.println("=====Destory=====");
    }
}
```

---

### Servlet 선언 및 맵핑

``` java
<servlet>
    <servlet-name>hello</servlet-name>
    <servlet-class>gid.HelloServlet</servlet-class>
  </servlet>
  
  <servlet-mapping>
    <servlet-name>hello</servlet-name>
    <url-pattern>/hello</url-pattern>
  </servlet-mapping>
```



import java.io.IOException;
import java.io.PrintWriter;

import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

/**
 * Servlet implementation class Simple
 */
@WebServlet("/Simple")
public class Simple extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    /**
     * @see HttpServlet#HttpServlet()
     */
    public Simple() {
        super();
        // TODO Auto-generated constructor stub
    }

	/**
	 * @see HttpServlet#service(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		// TODO Auto-generated method stub
		
		PrintWriter pw=response.getWriter();
		String name=request.getParameter("username");
		if(name.equals("neeraja"))
		{
			pw.println("Welcome "+name);
		}
		else
		{
			pw.println("Invalid User!!\nTry again!!!");
			//pw.println("");
			RequestDispatcher rd=request.getRequestDispatcher("Simple.html");
			rd.include(request, response);
		}
	}

}

package com.boardMVC.app.board;

import java.io.IOException;

import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import com.boardMVC.action.Action;
import com.boardMVC.action.ActionForward;
import com.boardMVC.app.board.dao.BoardDAO;

public class BoardDetailOk implements Action {

	@Override
	public ActionForward execute(HttpServletRequest req, HttpServletResponse resp) throws IOException {
		//사용자가 선택한 게시글 번호를 파라미터로 전달받는다.
		int boardNumber = Integer.parseInt(req.getParameter("boardNumber"));
		BoardDAO dao = new BoardDAO();
		ActionForward af = new ActionForward();
		
		//게시글 번호로 조회한 게시글의 전체 정보를 requestScope에 저장한다.
		req.setAttribute("board", dao.selectDetail(boardNumber));
		//상세보기로 왔다면, 조회수를 1 증가시켜준다.
		dao.updateReadCount(boardNumber);
		
		//requestScope에 데이터를 담았기 때문에 forward로 페이지까지 req객체를 유지한다.
		af.setRedirect(false);
		af.setPath("/app/board/boardDetail.jsp");
		
		return af;
	}

}

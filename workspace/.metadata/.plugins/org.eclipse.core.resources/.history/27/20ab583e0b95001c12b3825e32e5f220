package com.boardMVC.app.board.dao;

import java.util.List;
import java.util.Map;

import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;

import com.boardMVC.app.board.vo.BoardDTO;
import com.boardMVC.app.board.vo.BoardVO;
import com.boardMVC.mybatis.config.MyBatisConfig;

public class BoardDAO {
	SqlSessionFactory sqlSessionFactory = MyBatisConfig.getSqlsessoinFactory();
	SqlSession sqlSession;
	
	public BoardDAO() {
		sqlSession = sqlSessionFactory.openSession(true);
	}
	
	//게시글 목록
//	public List<BoardVO> selectAll(Map<String, Integer> boardMap) {
//		return sqlSession.selectList("Board.selectAll", boardMap);
//	}
	
	//게시글 목록
	public List<BoardDTO> selectAll(Map<String, Integer> boardMap) {
		return sqlSession.selectList("Board.selectAll", boardMap);
	}
	
	//게시글 전체 개수
	public int getTotal() {
		return sqlSession.selectOne("Board.getTotal");
	}
}

package com.boardMVC.app.board.dao;

import java.util.List;

import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;

import com.boardMVC.app.board.vo.BoardReplyDTO;
import com.boardMVC.mybatis.config.MyBatisConfig;

public class BoardReplyDAO {
	SqlSessionFactory sqlSessionFactory = MyBatisConfig.getSqlsessoinFactory();
	SqlSession sqlSession;
	
	public BoardReplyDAO() {
		sqlSession = sqlSessionFactory.openSession(true);
	}
	
	//댓글 목록
	public List<BoardReplyDTO> selectReplies(int boardNumber) {
		return sqlSession.selectList("Board.selectReplies", boardNumber);
	}
}

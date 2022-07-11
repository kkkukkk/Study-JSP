package com.boardMVC.app.member.dao;

import java.util.Map;

import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;

import com.boardMVC.app.member.vo.MemberVO;
import com.boardMVC.mybatis.config.MyBatisConfig;

public class MemberDAO {
	SqlSessionFactory sqlSessionFactory = MyBatisConfig.getSqlsessoinFactory();
	SqlSession sqlSession;
	
	public MemberDAO() {
		sqlSession = sqlSessionFactory.openSession(true);
	}
	
	//아이디 중복검사
	public boolean checkId(String memberId) {
		return (Integer)sqlSession.selectOne("Member.checkId", memberId) == 1;
	}
	
	//회원가입
	public void join(MemberVO member) {
		sqlSession.insert("Member.join", member);
	}
	
	//로그인
	public int login(Map<String, String> loginMap) {
		int memberNumber = 0;
		try {memberNumber = sqlSession.selectOne("Member.login", loginMap);} catch (Exception e) {;}
		return memberNumber;
	}
}













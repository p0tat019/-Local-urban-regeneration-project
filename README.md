# Local_urban_regeneration-project

1. Flask 프로젝트 설정
  
  
 a. 가상환경 생성 및 활성화
  
    # 가상환경 생성
    python -m venv venv
    
    # 가상환경 활성화 (Windows)
    venv\Scripts\activate
    
    # 가상환경 활성화 (Linux 또는 macOS)
    source venv/bin/activate
  
   b. Flask 설치
    
    pip install Flask

    
2. React 프로젝트 설정
   
     a. Node.js 및 npm 설치
      Node.js 및 npm을 설치하지 않았다면 Node.js 공식 웹사이트에서 다운로드하여 설치하세요.
      
   b. Create React App 설치
       npx create-react-app react_app
        cd react_app
   
3. 프로젝트 통합
   
   a. React 빌드

      npm run build
      이 명령을 실행하면 react_app/build 디렉토리에 React 애플리케이션의 빌드 결과물이 생성됩니다.

   b. Flask에서 정적 파일 서비스 설정 (app.py)

      from flask import Flask, render_template
      
      app = Flask(__name__, static_folder='react_app/build', static_url_path='/')

      @app.route('/')
      def index():
          return app.send_static_file('index.html')
      
      if __name__ == '__main__':
          app.run(debug=True)

4. 실행

     a. Flask 애플리케이션 실행

      python app.py

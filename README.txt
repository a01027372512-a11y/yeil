YEIL 운영관리 시스템 v2.1 - 로그인 진단판

YEIL 운영관리 시스템 v2 - Supabase 동기화

1. index.html을 실행합니다.
2. 첫 로그인 시 Supabase Publishable key(sb_publishable_...)를 한 번 입력합니다.
   - Supabase > Settings > API Keys > Publishable key > default에서 복사
   - Secret key는 절대 입력하지 마세요.
3. Authentication > Users에 만든 각자의 이메일/비밀번호로 로그인합니다.
4. 예약, 거래처, 비용 데이터는 Supabase에 저장됩니다.

실시간 자동 반영을 사용하려면 Supabase SQL Editor에서 아래 SQL을 1회 실행하세요.

alter publication supabase_realtime add table public.reservations;
alter publication supabase_realtime add table public.partners;
alter publication supabase_realtime add table public.costs;

주의: 이미 위 테이블을 Realtime publication에 추가했다면 같은 SQL을 다시 실행하지 마세요.


v2.1 변경사항:
- 로그인 실패 시 Supabase 실제 오류 코드/메시지 표시
- 로그인 화면에서 Publishable key 재설정 가능
- Supabase 연결 상태 확인 버튼 추가

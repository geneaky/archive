
enum을 class 이름으로 String형태로 응답으로 넘겨줄지, enum에 대한 value값을 넘겨줄지에 대한 고민이 있었다.

일단 enum에 숫자를 지정한 경우에 대해 생각해보면 해당 enum이 DB에 저장이 되어야하는 경우 int value값으로 저장시 쿼리에 조회 결과가 모호하다, string으로 저장한 경우는 의미가 들어나기 때문에 저
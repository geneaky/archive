
ManyToOne관계인 entit에서 Many쪽에 cascade remove를 적용한 경우
many를 직접 삭제할때 연관된 one쪽의 entity도 함께 삭제가 되지만 이는 삭제전 setOne(null)과 같이 연관관계를 끊어주고 삭제하는 방향으로 삭제에서 제외시킬 수 있는데 

ManyToOne관계인 entit에서 Many쪽에 cascade remove를 적용한 경우
many를 직접 삭제할때 연관된 one쪽의 entity도 함께 삭제가 되지만 이는 삭제전 setOne(null)과 같이 연관관계를 끊어주고 삭제하는 방향으로 삭제에서 제외시킬 수 있다

근데 manytoone에서 many쪽에 cascade remove를 거는 상황이 뭐가 있을까?
manytoone에서 one entity를 가지는 many entity가 2개 이상인 상황에서 전부를 지워주는게 아니라 하나만 delete하는 경우에는 delete가 실패하게되는데 결국 one과 연관관계를 가지는 모든 many쪽 entity를 다 찾아서 지워줘야 one쪽의 entity도 같이 삭제가되니 

> "멤버십 카드가 모두 사라지면 사실상 저희 카드의 멤버가 아니기 때문에 멤버에서 지워집니다"

와 같은 요구사항이 있을때가 있을듯 싶다


생각해보면 @OneToMany에 cascade를 거는게 많이 발생하는 요구사항 처리에 좋을듯 싶기도한데 
단방향 연관관계를 default로 가져가는 상황에서 cascade remove 하나 하겠다고 @OneToMany를 쓰는게 맞나 싶기도하다
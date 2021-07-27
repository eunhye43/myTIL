### Paginator란 무엇일까?
* 게시판과 같은 목록이 주어져있을 때, 페이지 당 몇 개의 글을 보여줄지 지정해줄 수 있도록 도와주는 내장모듈.
```
from django.core.paginator import Paginator #이렇게 임포트해주기
```

연습!
```
def product_list(requst):
    products = Product.objects.all() 
    # product에 있는거 다 불러와주고,
    
    paginator = Paginator(products, 3)
    # 한페이지당 '3'개를 보여주겠다는 의미
    
    page_number = int(request.GET.get("page",1))
    # request.GET.get("page")은 딕셔너리형."page"라는 key값을 인자로 주면 몇 페이지인지 value로 반환
    # urld의 쿼리 스트링에서 page에 해당하는 값을 가져올건데, page값 존재 안하면 1page 보여줄거야.
    
    page_obj = paginator.get_page(page_number)   
    # 전달받은 페이지번호(page_number)에 해당하는 게시글 오브젝트를 가지고 옴
```

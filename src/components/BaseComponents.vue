<script setup lang="ts">

import ReviewListItem from "@/components/review/list/ReviewListItem.vue";
import BookMainRecommendCard from "@/components/book/main/BookMainRecommendCard.vue";
import VConfirmPopup from "@/components/popup/VConfirmPopup.vue";
import VConfirmCancelPopup from "@/components/popup/VConfirmCancelPopup.vue";
import BookListHorizontalItem from "@/components/book/list/BookListHorizontalItem.vue";
import BookListVerticalItem from "@/components/book/list/BookListVerticalItem.vue";
import ReviewDetailCard from "@/components/review/detail/ReviewDetailCard.vue";
import BookDetailCard from "@/components/book/detail/card/BookDetailCard.vue";
import VErrorIcon from "@/components/error/VErrorIcon.vue";
import BookSaleButton from "@/components/book/BookSaleButton.vue";
import VLabel from "@/components/label/VLabel.vue";
import VRadioBox from "@/components/radiobox/VRadioBox.vue";
import BookDetailController from "@/components/book/detail/BookDetailController.vue";
import VSelectBox from "@/components/selectbox/VSelectBox.vue";
import ReviewStars from "@/components/review/SettableReviewStars.vue";
import MenuItem from "@/components/menu/MenuItem.vue";
import TheHeaderBar from "@/components/header/TheHeaderBar.vue";
import TheScmHeaderBar from "@/components/header/TheScmHeaderBar.vue";
import VAlarmIcon from "@/components/alarm/VAlarmButton.vue";
import VPlayButton from "@/components/music/VPlayButton.vue";
import VDeliveryStatusLabel from "@/components/label/VDeliveryStatusLabel.vue";
import VInquiryStatusLabel from "@/components/label/VInquiryStatusLabel.vue";
import TheNavigationBar from "@/components/navigation/TheNavigationBar.vue";
import VSmallButton from "@/components/button/VSmallButton.vue";
import VBigButton from "@/components/button/VBigButton.vue";
import VSubscribeButton from "@/components/button/VSubscribeButton.vue";
import VZzimKongButton from "@/components/zzim/VZzimKongButton.vue";
import VCheckBox from "@/components/checkbox/VCheckBox.vue";
</script>

<template>
  <h1>공용 컴포넌트</h1>
  <div>
    <h4>후기 미리보기</h4>
    <ReviewListItem
        cover-img-url="https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885__480.jpg"
        title="안녕, 둔촌주공아파트"
        :review-score="3"
        content="주공아파트는 무엇인가?"
    />
  </div>
  <div>
    <h4>메인추천카드</h4>
    <BookMainRecommendCard
        cover-img-url="https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885__480.jpg"
        title="겨울섬"
        :price="15000"
        :sales-rate="10"/>
  </div>
  <div>
    <h4>팝업</h4>
    <h6>확인팝업</h6>
    <VConfirmPopup
        message="만나서 반가워요!"
        confirm-button-text="확인"
    />
    <h6>확인취소팝업</h6>
    <VConfirmCancelPopup
        message="주문하실거에요?"
        confirm-button-text="네"
        cancel-button-text="아니요"
    />
  </div>
  <div>
    <h4>상품리스트</h4>
    <h6>가로</h6>
    <BookListHorizontalItem
        cover-img-url="https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885__480.jpg"
        title="안녕, 둔촌주공아파트"
        author-nickname="이인규"
        publisher="라야"
        :price="14900"
        :sales-rate="0"
        :categories="['사진집', '에세이']"
    />
    <h6>세로</h6>
    <BookListVerticalItem
        cover-img-url="https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885__480.jpg"
        title="록셔리 vol.2"
        publisher="스토리지북스"
        :price="15000"
        :sales-rate="10"
    />
  </div>
  <div>
    <h4>후기 카드</h4>
    <ReviewDetailCard
        author-nickname="홍길동"
        profile-img-url="https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885__480.jpg"
        :review-score="4"
        content="이 책은 정말 좋아요. 추천합니다."
    />
    <br>
    <ReviewDetailCard
        author-nickname="홍길동"
        profile-img-url="https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885__480.jpg"
        :review-score="4"
        content="이 책은 정말 좋아요. 추천합니다."
        :review-img-urls="[
            'https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885__480.jpg',
            'https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885__480.jpg',
            'https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885__480.jpg',
        ]"
    />
  </div>
  <div>
    <h4>상품정보 카드</h4>
    <BookDetailCard
        :book-id="1"
        title="안녕둔촌주공아파트"
        author-nickname="홍길동과 양반들"
        publisher="동해번쩍북스"
        :delivery-fee="3000"
        :price="20000"
        :sales-rate="10"
        :stock-count="4"
        :review-score="3.4"/>
    <br>
    <BookDetailCard
        :book-id="1"
        title="안녕둔촌주공아파트"
        author-nickname="홍길동과 양반들"
        publisher="동해번쩍북스"
        :delivery-fee="3000"
        :price="20000"
        :sales-rate="10"
        :stock-count="0"
        :review-score="3.4"/>
  </div>
  <div>
    <h4>에러 아이콘</h4>
    <VErrorIcon/>
  </div>
  <div>
    <h4>판매중지/재개버튼</h4>
    <BookSaleButton :onSale='true'/>
    <BookSaleButton :onSale='false'/>
  </div>
  <div style="display: flex; gap: 15px">
    <h4>라벨</h4>
    <div style="flex-direction: row">
      <h5>입점승인</h5>
      <VLabel label-type='승인완료'/>
      <VLabel label-type='반려'/>
      <VLabel label-type='검토중'/>
    </div>
    <div style="flex-direction: row">
      <h5>신간등록검토</h5>
      <VLabel label-type='미검토'/>
      <VLabel label-type='검토완료'/>
    </div>
    <div style="flex-direction: row">
      <h5>발송상태</h5>
      <VLabel label-type='승인완료'/>
      <VLabel label-type='접수완료'/>
      <VLabel label-type='발송완료'/>
      <VLabel label-type='배송완료'/>
      <VLabel label-type='취소처리'/>
    </div>
    <div style="flex-direction: row">
      <h5>카테고리</h5>
      <VLabel label-type='시집'/>
      <VLabel label-type='에세이'/>
      <VLabel label-type='여행'/>
      <VLabel label-type='사진집'/>
      <VLabel label-type='일러스트'/>
      <VLabel label-type='카툰'/>
      <VLabel label-type='매거진'/>
      <VLabel label-type='소설'/>
      <VLabel label-type='엽서'/>
      <VLabel label-type='스티커'/>
      <VLabel label-type='액세서리'/>
      <VLabel label-type='기타'/>
      <VLabel label-type='문화생활'/>
      <VLabel label-type='강좌'/>
    </div>
  </div>
  <div>
    <h4>라디오버튼</h4>
    <div style="display: flex">
      <VRadioBox :checked='true'/>
      <VRadioBox :checked='false'/>
    </div>
  </div>
  <div>
    <h4>도서 상세 페이지 컨트롤</h4>
    <BookDetailController/>
  </div>
  <div>
    <h4>정렬</h4>
    <h6>후기정렬기준</h6>
    <VSelectBox select-box-type="review"/>
    <h6>도서정렬기준</h6>
    <VSelectBox select-box-type="book"/>
  </div>
  <div>
    <h4>별점</h4>
    <ReviewStars/>
  </div>
  <div>
    <h4>메뉴 리스트</h4>
    <MenuItem menu-type="서평관리"/>
  </div>
  <div style="background-color: lightgray">
    <h4>독자용 상단바</h4>
    <TheHeaderBar page-title="여기에 제목"/>
    <hr>
    <h4>유통시스템 상단바</h4>
    <TheScmHeaderBar/>
    <hr>
  </div>
  <div style="background-color: gray">
    <h4>알림 아이콘</h4>
    <VAlarmIcon :has-alarm='true'/>
    <VAlarmIcon :has-alarm='false'/>
  </div>
  <div>
    <h4>플레이버튼</h4>
    <VPlayButton/>
    <hr>
  </div>
  <div>
    <h4>상태 컴포넌트</h4>
    <h6>배송상태</h6>
    <VDeliveryStatusLabel status="배송준비중"/>
    <VDeliveryStatusLabel status="배송중"/>
    <VDeliveryStatusLabel status="배송완료"/>
    <VDeliveryStatusLabel status="주문완료"/>
    <hr>
    <h6>문의상태</h6>
    <VInquiryStatusLabel status="미답변"/>
    <VInquiryStatusLabel status="답변완료"/>
  </div>
  <div>
    <h4>네비게이션바</h4>
    <TheNavigationBar/>
    <hr>
  </div>
  <div>
    <h4>버튼</h4>
    <div>
      <h5>소버튼</h5>
      <VSmallButton button-name='버튼' button-state="default"/>
      <br>
      <VSmallButton button-name='버튼' button-state="disabled"/>
      <br>
      <VSmallButton button-name='버튼' button-state="emphasis"/>
    </div>
    <div>
      <h5>대버튼</h5>
      <VBigButton button-name='버튼' button-state="default"/>
      <br>
      <VBigButton button-name='버튼' button-state="disabled"/>
      <br>
      <VBigButton button-name='버튼' button-state="emphasis"/>
    </div>
    <div>
      <h5>구독버튼</h5>
      <VSubscribeButton :is-subscribed='true'/>
      <br>
      <VSubscribeButton :is-subscribed='false'/>
    </div>
    <hr>
  </div>
  <div>
    <h4>찜콩</h4>
    <VZzimKongButton :is-zzim='true'/>
    <VZzimKongButton :is-zzim='false'/>
    <hr>
  </div>
  <div>
    <h4>체크박스</h4>
    <VCheckBox :checked='true'/>
    <VCheckBox :checked='false'/>
    <hr>
  </div>
</template>

<style scoped>

</style>
# cnn기반 이미지분류 사이트

## Supabase Storage 구조
Supabase Storage에 public bucket을 만들고 이름을 `cnn-images`로 둡니다.

```
cnn-images/
 ├─ apple/apple1.jpg ~ apple20.jpg
 ├─ cherry/cherry1.jpg ~ cherry20.jpg
 └─ test.jpg
```

## config.js 수정
`config.js`에서 아래 값을 채웁니다.

```js
window.APP_CONFIG = {
  SUPABASE_URL: "https://프로젝트ref.supabase.co",
  SUPABASE_ANON_KEY: "anon public key",
  BUCKET: "cnn-images"
};
```

## Vercel 배포
1. 이 폴더를 GitHub 저장소에 올립니다.
2. Vercel에서 Import Project를 누릅니다.
3. Framework Preset은 Other 또는 Static으로 둡니다.
4. 배포 후 나온 링크를 열면 됩니다.

## 사용 흐름
1. 사이트 접속
2. 자동 사전작업 확인
3. 학습 탭에서 `학습 시작` 클릭
4. 이미지 검증 탭에서 `자동 검증하고 확률분포 보기` 클릭

## 주의
- Storage bucket이 public이어야 이미지가 바로 불러와집니다.
- test.jpg는 bucket 루트에 있어야 자동 검증됩니다.

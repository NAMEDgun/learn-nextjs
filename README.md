# learn-nextjs

# 1. Getting Started

### 프로젝트 생성

- `pnpm` 을 package manager로 사용하도록 → `npm / yarn` 보다 빠르고 효율
- 특징
  1. **성능 최적화:** 패키치를 공유된 저장소에 저장 및 hard link를 사용하여 의존성 관리
  2. **공유 저장소:** 전역적으로 공유된 저장소 저장
  3. **일관된 의존성:** 동일한 의존성 트리 보장(예측 가능한 빌드 결과)
  4. **Strict Mode**: `node_modules` 폴더에서의 flat 한 구조 생성 X. 패키지를 고유한 dir에 저장하여, 의존성 충돌을 방지하고 디버깅 용이

```bash
npm install -g pnpm
npx create-next-app@latest nextjs-dashboard --example "https://github.com/vercel/next-learn/tree/main/dashboard/starter-example" --use-pnpm
```

- CLI 도구(create-next-app)

```bash
cd nextjs-dashboard
```

---

### 폴더 구조

- **/app**: 애플리케이션의 모든 라우트, 컴포넌트 및 로직이 들어있는 폴더로, 주로 이곳에서 작업하게 됩니다.
- **/app/lib**: 재사용 가능한 유틸리티 함수 및 데이터 가져오기 함수와 같은 애플리케이션에서 사용되는 함수들이 들어있습니다.
- **/app/ui**: 카드, 테이블, 폼과 같은 UI 컴포넌트들이 들어있습니다. 이 컴포넌트들은 미리 스타일이 적용되어 있습니다.
- **/public**: 이미지와 같은 애플리케이션의 정적 자산들이 들어있습니다.
- **Config Files**: 프로젝트 루트에는 `next.config.js`와 같은 설정 파일들이 있습니다. 대부분의 설정 파일들은 create-next-app을 사용해 새 프로젝트를 시작할 때 생성되고 미리 구성됩니다. 이 코스에서는 이러한 파일들을 수정할 필요가 없습니다.

---

### Placeholder data

> 데이터베이스나 API가 아직 준비되지 않은 경우

- JSON 형식의 플레이스홀더 데이터 또는 자바스크립트 객체
- mockAPI와 같은 3rd 파티 서비스
- `app/lib/placeholder-data.ts`

```tsx
const invoices = [
  {
    customer_id: customers[0].id,
    amount: 15795,
    status: "pending",
    date: "2022-12-06",
  },
  {
    customer_id: customers[1].id,
    amount: 20348,
    status: "pending",
    date: "2022-11-14",
  },
  // ...
];
```

---

### Typescript

- `.ts` / `.tsx` 확장자
- `/app/lib/definitions.ts`

```tsx
export type Invoice = {
  id: string;
  customer_id: string;
  amount: number;
  date: string;
  status: "pending" | "paid";
};
```

---

### 개발 서버 실행

- project package install

```bash
pnpm i
pnpm dev
```

---

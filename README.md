# tenten-workflow

## I. Quản lý mã nguồn với Git: Sử dụng 2 nhánh release và 1 nhánh chính (main)

Để quản lý mã nguồn hiệu quả cho dự án của bạn với Git, việc sử dụng 2 nhánh release dành cho thành viên và 1 nhánh chính (main) là một phương pháp phổ biến. Cách thức hoạt động như sau:

**1. Nhánh chính (main):**

* Là nhánh trung tâm lưu trữ mã nguồn ổn định và đã được thử nghiệm kỹ lưỡng.
* Nên được bảo vệ để tránh các thay đổi trực tiếp.
* Sử dụng để tạo các bản release chính thức cho dự án.

**2. Nhánh release:**

* Tạo ra từ nhánh chính (main) cho mỗi bản release mới.
* Dùng để thực hiện các thay đổi và sửa lỗi cho bản release sắp tới.
* Sau khi hoàn tất, nhánh release được sáp nhập vào nhánh chính (main) và tạo tag để đánh dấu bản release.

**Quy trình làm việc:**

1. **Bắt đầu từ nhánh chính (main):**
    * Lấy mã nguồn mới nhất từ nhánh chính (main) về máy cục bộ.
    * Bắt đầu thực hiện các thay đổi và sửa lỗi cho bản release tiếp theo.
2. **Tạo nhánh release:**
    * Khi bạn đã sẵn sàng cho bản release mới, hãy tạo một nhánh release mới từ nhánh chính (main).
    * Ví dụ: `git branch release/v1.0.0`.
3. **Làm việc trên nhánh release:**
    * Chuyển sang nhánh release đã tạo: `git checkout release/v1.0.0`.
    * Thực hiện các thay đổi và sửa lỗi cần thiết cho bản release.
    * Thường xuyên commit và push thay đổi của bạn lên nhánh release.
4. **Kiểm tra và sáp nhập nhánh release:**
    * Sau khi hoàn tất việc phát triển bản release, hãy chuyển sang nhánh release và thực hiện lệnh `git checkout main`.
    * Lấy mã nguồn mới nhất từ nhánh release về nhánh chính: `git merge release/v1.0.0`.
    * Giải quyết xung đột (nếu có) xảy ra trong quá trình merge.
    * Push thay đổi lên nhánh chính (main).
5. **Tạo tag cho bản release:**
    * Chuyển sang nhánh chính (main): `git checkout main`.
    * Tạo tag cho bản release: `git tag v1.0.0`.
    * Push tag lên nhánh chính (main): `git push --tags`.
6. **Phát hành bản release:**
    * Sau khi tạo tag, bạn có thể tiến hành publish bản release cho người dùng.

**Lưu ý:**

* Nên sử dụng Git Flow hoặc GitLab Flow để có quy trình làm việc rõ ràng và hiệu quả hơn.
* Sử dụng code review để đảm bảo chất lượng mã nguồn trước khi merge vào nhánh chính (main).
* Việc sử dụng nhánh release giúp bảo vệ nhánh chính (main) khỏi các thay đổi không mong muốn và đảm bảo tính ổn định cho bản release chính thức.

**Tài liệu tham khảo:**

* [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/comparing-workflows)
* [GitHub workflow](https://docs.github.com/en/get-started/using-github/github-flow)
* [GitLab Flow](https://about.gitlab.com/topics/version-control/what-is-gitlab-flow/)

-------------------------------------------------
## II. Thông báo cho Team Lead rằng bạn đã hoàn thành công việc và chờ anh ấy review code

Để thông báo cho Team Lead rằng bạn đã hoàn thành công việc và chờ anh ấy review code, bạn có thể thực hiện theo các bước sau đây:

### 1. Đẩy code lên repository từ xa
Đảm bảo rằng tất cả các thay đổi của bạn đã được commit và đẩy lên repository từ xa trên nhánh release mà bạn đang làm việc.

```sh
git add .
git commit -m "Complete feature X"
git push origin release-branch-name
```

### 2. Tạo một Pull Request (PR) / Merge Request (MR)
Nếu bạn đang sử dụng một nền tảng quản lý mã nguồn như GitHub, GitLab, hoặc Bitbucket, bạn có thể tạo một Pull Request (PR) hoặc Merge Request (MR) để yêu cầu review code. Các bước dưới đây sẽ hướng dẫn tạo PR trên GitHub:

- **Truy cập repository trên GitHub:**
  - Mở trình duyệt web và truy cập vào repository của bạn trên GitHub.
  
- **Tạo Pull Request:**
  - Chọn tab "Pull requests".
  - Nhấp vào nút "New pull request".
  - Chọn nhánh gốc (main) và nhánh mà bạn đã làm việc (release-branch-name).
  - Nhấp vào "Create pull request".
  - Điền tiêu đề và mô tả chi tiết về những gì bạn đã làm trong Pull Request. Điều này giúp Team Lead hiểu rõ những thay đổi mà bạn đã thực hiện.
  - Gán người review (Team Lead) vào Pull Request.

### 3. Thông báo cho Team Lead
Sau khi tạo Pull Request, bạn cần thông báo cho Team Lead rằng bạn đã hoàn thành công việc và đang chờ review. Bạn có thể sử dụng một số phương pháp sau:

#### Qua email
- Soạn một email với tiêu đề và nội dung rõ ràng.
  - **Tiêu đề:** [Project Name] Code Review Request for Feature X
  - **Nội dung:**
    ```
    Hi [Team Lead's Name],

    I have completed the implementation of feature X and pushed the changes to the branch [release-branch-name]. 
    A pull request has been created for your review. Please take a look when you have the time.

    PR Link: [Insert Pull Request Link]

    Thank you,
    [Your Name]
    ```

#### Qua công cụ chat của công ty (Slack, Microsoft Teams, etc.)
- Gửi tin nhắn trực tiếp hoặc thông báo trong kênh phù hợp.
  ```
  Hi @TeamLead,

  I have completed the implementation of feature X and pushed the changes to the branch [release-branch-name]. 
  A pull request has been created for your review. Please take a look when you have the time.

  PR Link: [Insert Pull Request Link]

  Thank you!
  ```

#### Qua hệ thống quản lý công việc (Jira, Trello, etc.)
- Cập nhật trạng thái của task/ticket liên quan và thêm nhận xét (comment) để thông báo cho Team Lead.
  ```
  Feature X is implemented and ready for review. Please see the pull request: [Insert Pull Request Link]
  ```

### 4. Theo dõi quá trình review
Sau khi thông báo, theo dõi quá trình review và sẵn sàng trả lời các câu hỏi hoặc thực hiện các thay đổi cần thiết theo phản hồi từ Team Lead.

### Tóm lại
- Đảm bảo code đã được đẩy lên repository từ xa.
- Tạo Pull Request/Merge Request.
- Thông báo cho Team Lead qua email, công cụ chat, hoặc hệ thống quản lý công việc.
- Theo dõi quá trình review và thực hiện các thay đổi nếu cần thiết.

Những bước này sẽ giúp quá trình giao tiếp và review code diễn ra suôn sẻ và hiệu quả.

------------------------------------
## III. Nếu bạn đã chỉnh sửa nhánh `main` và cần sửa chữa một nhánh khác (`feature-branch`) để phù hợp
Nếu bạn đã chỉnh sửa nhánh `main` và cần sửa chữa một nhánh khác (`feature-branch`) để phù hợp với những thay đổi mới trên `main`, bạn có thể thực hiện các bước sau đây:

### 1. Cập nhật nhánh `main` từ repository từ xa
Đảm bảo rằng nhánh `main` của bạn đã được cập nhật với các thay đổi mới nhất từ repository từ xa.

```sh
git checkout main
git pull origin main
```

### 2. Chuyển sang nhánh `feature-branch`
Chuyển sang nhánh mà bạn muốn cập nhật.

```sh
git checkout feature-branch
```

### 3. Hợp nhất (merge) nhánh `main` vào `feature-branch`
Hợp nhất nhánh `main` vào `feature-branch` để cập nhật các thay đổi mới nhất từ `main`.

```sh
git merge main
```

Trong quá trình hợp nhất, có thể xảy ra xung đột (conflicts) nếu các thay đổi trên hai nhánh không tương thích với nhau. Bạn sẽ cần phải giải quyết các xung đột này thủ công.

### 4. Giải quyết xung đột (nếu có)
Mở các file có xung đột và chỉnh sửa để giải quyết các xung đột. Sau khi giải quyết xong, đánh dấu các xung đột đã được giải quyết bằng lệnh `git add`.

```sh
git add .
```

### 5. Hoàn thành quá trình hợp nhất
Sau khi giải quyết xong tất cả các xung đột, hoàn thành quá trình hợp nhất bằng cách commit các thay đổi.

```sh
git commit
```

### 6. Đẩy các thay đổi lên repository từ xa
Cuối cùng, đẩy các thay đổi trên nhánh `feature-branch` lên repository từ xa.

```sh
git push origin feature-branch
```

### Tóm tắt các bước
1. **Cập nhật nhánh `main`:**
    ```sh
    git checkout main
    git pull origin main
    ```
2. **Chuyển sang nhánh `feature-branch`:**
    ```sh
    git checkout feature-branch
    ```
3. **Hợp nhất `main` vào `feature-branch`:**
    ```sh
    git merge main
    ```
4. **Giải quyết xung đột (nếu có):**
    ```sh
    git add .
    ```
5. **Hoàn thành quá trình hợp nhất:**
    ```sh
    git commit
    ```
6. **Đẩy các thay đổi lên repository từ xa:**
    ```sh
    git push origin feature-branch
    ```

Bằng cách này, nhánh `feature-branch` của bạn sẽ được cập nhật với các thay đổi mới nhất từ nhánh `main`.

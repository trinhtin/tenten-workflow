# tenten-workflow

## Quản lý mã nguồn với Git: Sử dụng 2 nhánh release và 1 nhánh chính (main)

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


Ngoài ra, bạn có thể tham khảo thêm các tài liệu và khóa học online về Git để nâng cao kiến thức và kỹ năng quản lý mã nguồn hiệu quả.

Chúc bạn thành công!


-------------------------------------------------


# Quản lý mã nguồn với Git: Sử dụng 2 nhánh release và 1 nhánh chính (main)

This document describes a popular workflow for managing source code with Git using two release branches and one main branch.

## Branches

* **main branch:**
    * The central branch that stores stable and well-tested source code.
    * Should be protected to avoid direct changes.
    * Used to create official releases for the project.
* **release branches:**
    * Created from the main branch for each new release.
    * Used to implement changes and bug fixes for the upcoming release.
    * Once completed, the release branch is merged into the main branch and a tag is created to mark the release.

## Workflow

1. **Start from the main branch:**
    * Clone the latest source code from the main branch to your local machine.
    * Begin working on changes and bug fixes for the next release.
2. **Create a release branch:**
    * When you're ready for a new release, create a new release branch from the main branch.
    * Example: `git branch release/v1.0.0`
3. **Work on the release branch:**
    * Switch to the created release branch: `git checkout release/v1.0.0`
    * Make the necessary changes and bug fixes for the release.
    * Frequently commit and push your changes to the release branch.
4. **Review and merge the release branch:**
    * After completing the release development, switch to the release branch and run `git checkout main`.
    * Merge the latest code from the release branch into the main branch: `git merge release/v1.0.0`.
    * Resolve any conflicts (if any) that arise during the merge process.
    * Push the changes to the main branch.
5. **Create a tag for the release:**
    * Switch to the main branch: `git checkout main`
    * Create a tag for the release: `git tag v1.0.0`
    * Push the tag to the main branch: `git push --tags`
6. **Release the software:**
    * After creating the tag, you can proceed with publishing the release to users.

##  Additional Notes

* Consider using Git Flow or GitLab Flow for a clearer and more efficient workflow.
* Utilize code review to ensure code quality before merging into the main branch.
* Employing release branches helps safeguard the main branch from unwanted changes and guarantees stability for official releases. 

## References

* [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/comparing-workflows)
* [GitHub workflow](https://docs.github.com/en/get-started/using-github/github-flow)
* [GitLab Flow](https://about.gitlab.com/topics/version-control/what-is-gitlab-flow/)

For further information, explore additional resources and online courses on Git to enhance your knowledge and proficiency in source code management.

I hope this helps!

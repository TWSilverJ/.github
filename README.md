# .github

TWSilverJ 組織依 [ProjectWorkflow](https://github.com/TWSilverJ/ProjectWorkflow) 規範的實作，作為組織內所有專案共同遵守的規則。

## 用途

本儲存庫提供：

- **組織預設的範本**：議題範本與 PR 範本。
- **標籤**：標籤定義檔，以及把標籤套用到各儲存庫的同步腳本。
- **發版流程**：發版時建立 release，再由負責人以同步腳本把標籤套用到組織內所有未封存的儲存庫。

其中標籤與發版流程尚未提供，各節的說明會在項目完成時補上。

## 與 ProjectWorkflow 的關係

ProjectWorkflow 是規範，本儲存庫是規範的實作。

- 規範與實作衝突時，以規範為準。
- 範本與標籤的調整，從本儲存庫的議題開始。
- 需要修改規範時，先在 ProjectWorkflow 處理，再調整本儲存庫。

## 新儲存庫的導入步驟

1. **範本**：儲存庫不自帶議題範本與 PR 範本時，會自動套用本儲存庫的範本，不需要額外操作。
2. **標籤**：由負責人以同步腳本，把標籤套用到新的儲存庫。

   > [!NOTE]
   > 同步腳本尚未提供，目前還無法依這個步驟套用標籤。

## 範本

組織預設的議題範本與 PR 範本，放在 `.github/`：

- `ISSUE_TEMPLATE/`：一般議題、需求議題、問題回報、資訊安全四個議題範本，以及 `config.yml`。需求議題設定議題類型 Feature，問題回報與資訊安全設定 Bug。
- `pull_request_template.md`：PR 範本。

### 來源

範本取自 ProjectWorkflow 的 commit [82a52b4](https://github.com/TWSilverJ/ProjectWorkflow/tree/82a52b4/.github)，內容不做修改。

### 套用條件

儲存庫中不存在以下資料夾與檔案時，才會套用本儲存庫的範本。議題範本與 PR 範本分開判斷：

- **議題範本**：儲存庫中沒有 `.github/ISSUE_TEMPLATE/` 資料夾。
- **PR 範本**：儲存庫的根目錄、`.github/`、`docs/` 中，都沒有 `pull_request_template.md` 檔案或 `PULL_REQUEST_TEMPLATE/` 資料夾。

議題範本是全有或全無：儲存庫只要有 `.github/ISSUE_TEMPLATE/` 資料夾，即使其中只有一個範本或只有 `config.yml`，本儲存庫的議題範本就全部不套用。

### 更新方式

ProjectWorkflow 的範本變更合併後，以新的 commit 重新取用：

1. 以 ProjectWorkflow 新的 commit 中的 `.github/ISSUE_TEMPLATE/` 與 `.github/pull_request_template.md`，取代本儲存庫 `.github/` 中的對應檔案，內容不做修改。來源已刪除的範本，本儲存庫也一併刪除。
2. 將「來源」中的 commit 改為新的 commit。
3. 以 PR 提交，合併後生效。

## 標籤

> [!NOTE]
> 尚未提供。

以一份標籤定義檔集中管理標籤，由負責人以同步腳本套用到組織內的儲存庫。

## 發版流程

> [!NOTE]
> 尚未提供。

發版時建立 release，再由負責人以同步腳本，把該版本的標籤套用到組織內所有未封存的儲存庫。

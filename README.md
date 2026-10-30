# draft

## 3. Flowchart

- Embed your flowchart image here:

  ![Preprocessing Flowchart](flowchart/_Flowchart_Pair1Surname_Pair2Surname.png)

- **Decisions in our flowchart:**

  | # | Decision diamond | Condition checked | YES branch | NO branch |
  |---|------------------|-------------------|------------|-----------|
  | 1 | **Missing values?** | `df.isnull().sum() > 0` across any of the 12 columns | Handle missing values by column role (IDs & dates, pricing & quantity, categoricals, text), then continue | Skip to duplicate check |
  | 2 | **Duplicate rows?** | `df.duplicated().sum() > 0` | Deduplicate and consolidate order lines: drop exact full-row duplicates and resolve partial key collisions, then continue | Skip to data type conversion |
  | 3 | **Outliers detected?** | IQR / Z-score check on `quantity`, `unit_price`, `total_price` | Filter invalid records (invalid values, formula audit of `total_price = quantity × unit_price`) and cap statistical outliers, then continue | Skip to categorical encoding |
  | 4 | **More plots?** | `i < 10` | Return to the visualization loop: make plot, caption, save | Exit loop and go to **END** |

- **Changes we made:**
  - Changed ___ from ___ to ___ because ___.
  - Added ___ step that was not in the original flowchart because ___.
  - Removed ___ because the data had no ___.

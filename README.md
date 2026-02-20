# Sudoku Solver with MRV Heuristic

A high-performance Sudoku solver implemented in Python, featuring standard backtracking and the **Minimum Remaining Values (MRV)** heuristic for optimized search performance.

## Features

- **Backtracking Algorithm**: A reliable base implementation for solving any 9x9 Sudoku.
- **MRV Heuristic**: Dynamic cell selection based on the fewest remaining possibilities to minimize search branching.
- **Early Exit Optimization**: Instant selection of cells with only one possible value to accelerate the solving process.
- **Performance Analysis**: Automatic tracking and comparison of "Backtrack counts" between Standard and MRV methods.
- **Difficulty Integration**: Supports various difficulty levels (Easy to God) powered by the `dokusan` library.

## Installation

Ensure you have Python 3 installed. Install the required dependencies using pip:

```bash
pip install numpy dokusan
```

## Usage

Run the main script to start the interactive solver:

```bash
python sudoku.py
```

Follow the on-screen prompts to:
1. Select a difficulty level (1-7).
2. View the initial puzzle generated.
3. Observe the comparison of Backtrack counts between the two algorithms.
4. View the final solved board.

## Project Structure

- `sudoku.py`: The core implementation containing the `Sudoku` class and solving logic.
- `Assignment3_Sudoku.pdf`: The formal assignment requirements and background.
- `รายงาน_Sudoku_Assignment3_1.docx`: Documentation and project report (Thai).

---

## รายงาน Programming Assignment 3
### การพัฒนาโปรแกรมแก้ปัญหา Sudoku ด้วย Backtracking และ MRV Heuristic

#### 1. วัตถุประสงค์
พัฒนาโปรแกรมแก้ปัญหา Sudoku ขนาด 9x9 โดยเปรียบเทียบประสิทธิภาพระหว่าง **Backtracking แบบมาตรฐาน** และ **MRV Heuristic** โดยใช้จำนวนครั้งของการ Backtrack เป็นตัวชี้วัดความเร็วในการค้นหาคำตอบ

#### 2. อัลกอริทึมที่ใช้
- **Standard Backtracking**: ค้นหาช่องว่างเรียงตามลำดับแถวและคอลัมน์ แล้วทดลองใส่ตัวเลข 1-9
- **MRV (Minimum Remaining Values)**: เลือกช่องว่างที่มีจำนวนตัวเลขที่เป็นไปได้ (Legal moves) น้อยที่สุดก่อน เพื่อลดความกว้างของ Search Tree
- **Optimization**: เพิ่มระบบ **Early Exit** หากพบช่องที่มีค่าที่เป็นไปได้เพียงค่าเดียว จะทำการเลือกช่องนั้นทันทีโดยไม่ต้องคำนวณช่องอื่นต่อ

#### 3. การวิเคราะห์ประสิทธิภาพ
จากการทดสอบพบว่า MRV Heuristic สามารถลดจำนวนครั้งของการ Backtrack ได้อย่างมหาศาล โดยเฉพาะในระดับความยากสูง (เช่น Hard, Expert หรือ God) ซึ่งมักมีความซับซ้อนเชิงเวลา (Time Complexity) ในกรณีเลวร้ายที่สุดถึง $O(9^{81})$ แต่ด้วย MRV ทำให้เราสามารถบีบ Search Space ให้เล็กลงได้อย่างมีนัยสำคัญ

#### 4. ไลบรารีที่เกี่ยวข้อง
- `numpy`: ใช้สำหรับจัดการโครงสร้างข้อมูลตาราง 9x9 และการประมวลผลอาเรย์
- `dokusan`: ใช้สำหรับ Generate Sudoku Puzzle ตามระดับความยากที่ต้องการ

---

## Further Development
- [ ] Implement **Forward Checking** to detect failures earlier.
- [ ] Add **Constraint Propagation** (e.g., Naked Singles/Pairs).
- [ ] Integrate **Least Constraining Value (LCV)** heuristic.
- [ ] Visual UI for real-time solving steps.

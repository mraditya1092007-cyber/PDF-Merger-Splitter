from PyPDF2 import PdfMerger, PdfReader, PdfWriter

def merge_pdfs():
    pdf1 = input("First PDF path: ")
    pdf2 = input("Second PDF path: ")

    merger = PdfMerger()
    merger.append(pdf1)
    merger.append(pdf2)

    output = "merged.pdf"
    merger.write(output)
    merger.close()

    print(f"\nSuccess! Merged PDF saved as {output}")


def split_pdf():
    pdf_path = input("PDF path: ")

    reader = PdfReader(pdf_path)

    for i in range(len(reader.pages)):
        writer = PdfWriter()
        writer.add_page(reader.pages[i])

        output = f"page_{i+1}.pdf"

        with open(output, "wb") as file:
            writer.write(file)

    print("\nSuccess! PDF split into separate pages.")


def extract_text():
    pdf_path = input("PDF path: ")

    reader = PdfReader(pdf_path)

    with open("extracted_text.txt", "w", encoding="utf-8") as file:
        for page in reader.pages:
            text = page.extract_text()
            if text:
                file.write(text + "\n\n")

    print("\nSuccess! Text extracted to extracted_text.txt")


def pdf_info():
    pdf_path = input("PDF path: ")

    reader = PdfReader(pdf_path)

    print("\n===== PDF INFORMATION =====")
    print("Total Pages :", len(reader.pages))

    metadata = reader.metadata

    if metadata:
        print("Title :", metadata.get("/Title", "Not Available"))
        print("Author :", metadata.get("/Author", "Not Available"))
        print("Creator :", metadata.get("/Creator", "Not Available"))
    else:
        print("No metadata found.")

    print("===========================")


while True:
    print("\n===== PDF MERGER & SPLITTER =====")
    print("1. Merge PDF")
    print("2. Split PDF")
    print("3. Extract Text")
    print("4. PDF Info")
    print("5. Exit")

    choice = input("Enter choice (1-5): ")

    if choice == "1":
        merge_pdfs()

    elif choice == "2":
        split_pdf()

    elif choice == "3":
        extract_text()

    elif choice == "4":
        pdf_info()

    elif choice == "5":
        print("Exiting Program...")
        break

    else:
        print("Invalid Choice! Please try again.")

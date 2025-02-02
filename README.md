import logging

# Configure logging
logging.basicConfig(filename="pdf_operations.log", level=logging.INFO, format="%(asctime)s - %(message)s")

def main():
    print("PDF Merger and Splitter")
    print("1. Merge PDFs")
    print("2. Split PDF")
    choice = input("Enter your choice (1 or 2): ")

    if choice == "1":
        input_files = input("Enter the paths of the PDF files to merge (comma-separated): ").split(",")
        output_file = input("Enter the output file name (e.g., merged.pdf): ")
        try:
            merge_pdfs(input_files, output_file)
            logging.info(f"Merged PDFs: {input_files} into {output_file}")
        except Exception as e:
            print(f"Error: {e}")
            logging.error(f"Error merging PDFs: {e}")

    elif choice == "2":
        input_file = input("Enter the path of the PDF file to split: ")
        output_folder = input("Enter the output folder name: ")
        try:
            split_pdf(input_file, output_folder)
            logging.info(f"Split PDF: {input_file} into {output_folder}")
        except Exception as e:
            print(f"Error: {e}")
            logging.error(f"Error splitting PDF: {e}")

    else:
        print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()

#create a tool that takes info from 
# resumes and pair them to job descriptions
#using NLP adn oop to manage the parsing matching and UI layers


#using streamlit for the UI
import os
import streamlit as st

class FileManager:
    """Manages file reading for resumes and job descriptions."""
    def __init__(self, resume_path, job_desc_paths):
        self.resume_path = resume_path
        self.job_desc_paths = job_desc_paths

    def read_file(self, file_path):
        if not os.path.exists(file_path):
            raise FileNotFoundError(f"{file_path} does not exist.")
        with open(file_path, 'r') as file:
            return file.read()

    def get_resumes(self):
        return self.read_file(self.resume_path)

    def get_job_descriptions(self):
        job_descriptions = []
        for path in self.job_desc_paths:
            job_descriptions.append(self.read_file(path))
        return job_descriptions

class TextProcessor:
    """Processes text data for comparison."""
    @staticmethod
    def to_word_set(text):
        # Split text into words, normalize case, and remove duplicates
        return set(word.lower() for word in text.split())

    @staticmethod
    def find_common_words(text1, text2):
        words1 = TextProcessor.to_word_set(text1)
        words2 = TextProcessor.to_word_set(text2)
        return words1.intersection(words2)

class Matcher:
    """Matches resumes to multiple job descriptions based on common words."""
    def __init__(self, resume_path, job_desc_paths):
        self.file_manager = FileManager(resume_path, job_desc_paths)

    def match(self):
        try:
            resumes = self.file_manager.get_resumes()
            job_descriptions = self.file_manager.get_job_descriptions()
            results = {}
            for i, job_desc in enumerate(job_descriptions):
                common_words = TextProcessor.find_common_words(resumes, job_desc)
                results[f"Job Description {i + 1}"] = common_words
            return results
        except FileNotFoundError as e:
            st.error(e)
            return {}

# Streamlit UI
st.title("Resume and Job Description Matcher")

resume_file_path = st.text_input("Enter the path to the resumes file:")
job_description_file_paths = st.text_area(
    "Enter the paths to job description files (one per line):"
).splitlines()

if st.button("Match"):
    if resume_file_path and job_description_file_paths:
        matcher = Matcher(resume_file_path, job_description_file_paths)
        results = matcher.match()
        if results:
            for job_desc, common_words in results.items():
                st.write(f"{job_desc}: {common_words}")
        else:
            st.write("No common words found or an error occurred.")
    else:
        st.error("Please provide the resume file path and at least one job description file path.")


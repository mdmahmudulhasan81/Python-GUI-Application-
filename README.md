# Python_GUI_Application
import tkinter as tk
from tkinter import ttk


def save_cv():
    personal_info = {
        "Name": entry_name.get(),
        "Email": entry_email.get(),
        "Phone": entry_phone.get(),
        "Address": entry_address.get()
    }
    education_info = {
        "Degree": entry_degree.get(),
        "University": entry_university.get(),
        "Year": entry_year.get()
    }
    work_experience = {
        "Company": entry_company.get(),
        "Role": entry_role.get(),
        "Years": entry_years.get()
    }
    skills = entry_skills.get("1.0", tk.END).strip()
    with open('cv_data.txt', 'w') as f:
        f.write("Personal Information\n")
        for key, value in personal_info.items():
            f.write(f"{key}: {value}\n")
        f.write("\nEducation\n")
        for key, value in education_info.items():
            f.write(f"{key}: {value}\n")
        f.write("\nWork Experience\n")
        for key, value in work_experience.items():
            f.write(f"{key}: {value}\n")
        f.write("\nSkills\n")
        f.write(f"{skills}\n")

  print("CV saved successfully!")
root = tk.Tk()
root.title("CV Builder")


ttk.Label(root, text="Personal Information").grid(column=0, row=0, padx=10, pady=10, columnspan=2)

ttk.Label(root, text="Name:").grid(column=0, row=1, sticky=tk.W)
entry_name = ttk.Entry(root, width=30)
entry_name.grid(column=1, row=1)

ttk.Label(root, text="Email:").grid(column=0, row=2, sticky=tk.W)
entry_email = ttk.Entry(root, width=30)
entry_email.grid(column=1, row=2)

ttk.Label(root, text="Phone:").grid(column=0, row=3, sticky=tk.W)
entry_phone = ttk.Entry(root, width=30)
entry_phone.grid(column=1, row=3)

ttk.Label(root, text="Address:").grid(column=0, row=4, sticky=tk.W)
entry_address = ttk.Entry(root, width=30)
entry_address.grid(column=1, row=4)

ttk.Label(root, text="Education").grid(column=0, row=5, padx=10, pady=10, columnspan=2)

ttk.Label(root, text="Degree:").grid(column=0, row=6, sticky=tk.W)
entry_degree = ttk.Entry(root, width=30)
entry_degree.grid(column=1, row=6)

ttk.Label(root, text="University:").grid(column=0, row=7, sticky=tk.W)
entry_university = ttk.Entry(root, width=30)
entry_university.grid(column=1, row=7)

ttk.Label(root, text="Year:").grid(column=0, row=8, sticky=tk.W)
entry_year = ttk.Entry(root, width=30)
entry_year.grid(column=1, row=8)


ttk.Label(root, text="Work Experience").grid(column=0, row=9, padx=10, pady=10, columnspan=2)

ttk.Label(root, text="Company:").grid(column=0, row=10, sticky=tk.W)
entry_company = ttk.Entry(root, width=30)
entry_company.grid(column=1, row=10)

ttk.Label(root, text="Role:").grid(column=0, row=11, sticky=tk.W)
entry_role = ttk.Entry(root, width=30)
entry_role.grid(column=1, row=11)

ttk.Label(root, text="Years:").grid(column=0, row=12, sticky=tk.W)
entry_years = ttk.Entry(root, width=30)
entry_years.grid(column=1, row=12)


ttk.Label(root, text="Skills:").grid(column=0, row=13, sticky=tk.W)
entry_skills = tk.Text(root, height=5, width=30)
entry_skills.grid(column=1, row=13)


submit_button = ttk.Button(root, text="Save CV", command=save_cv)
submit_button.grid(column=0, row=14, columnspan=2, pady=20)

root.mainloop()

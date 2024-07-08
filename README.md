# python-resume
Guide to creating a resume using Python


# Crafting the Perfect Data Engineering Resume with Python

Creating a professional resume can be a daunting task, but what if you could automate the process using Python? Today, we'll dive into how you can leverage the `reportlab` library to create a polished and professional data engineering resume. This guide will walk you through the steps, complete with code snippets, to help you build your resume from scratch.

## Getting Started

First things first, you'll need to install the `reportlab` library. If you haven't already, you can do so using pip:

```bash
pip install reportlab

```
## Setting Up Your Document
We'll start by importing the necessary libraries and setting up our document structure.

python code: 

    from reportlab.lib.pagesizes import letter
    from reportlab.lib.styles import getSampleStyleSheet, ParagraphStyle
    from reportlab.lib.units import inch
    from reportlab.platypus import Paragraph, SimpleDocTemplate, Spacer
    from reportlab.lib import colors

    def create_pdf(file_path):
        doc = SimpleDocTemplate(file_path, pagesize=letter, rightMargin=0.75*inch, leftMargin=0.75*inch, topMargin=0.5*inch, bottomMargin=0.5*inch)
        styles = getSampleStyleSheet()
    
## Customizing Styles
Next, we'll create custom styles to ensure our resume looks professional and well-organized.

python code: 

    title_style = ParagraphStyle(
        name='TitleStyle',
        fontSize=20,
        leading=24,
        alignment=1,
        fontName='Times-Roman'
    )
    
    contact_style = ParagraphStyle(
        name='ContactStyle',
        fontSize=12,
        leading=14,
        alignment=1,
        fontName='Times-Roman'
    )

    subtitle_style = ParagraphStyle(
        name='SubtitleStyle',
        fontSize=14,
        leading=18,
        spaceAfter=14,
        fontName='Times-Roman',
        textColor=colors.HexColor("#333333")
    )
    
    normal_style = ParagraphStyle(
        name='NormalStyle',
        fontSize=10,
        leading=12,
        spaceAfter=10,
        fontName='Times-Roman'
    )
    
    profile_style = ParagraphStyle(
        name='ProfileStyle',
        fontSize=12,
        leading=14,
        spaceAfter=14,
        fontName='Times-Roman',
        textColor=colors.HexColor("#333333")
    )
## Building the Resume Content
Now, let's add the content to our resume. We'll create sections for the title, contact information, professional summary, technical skills, professional experience, education, and professional competencies.

python code:

    # Title and Contact Information
    elements.append(Paragraph("John Doe", title_style))
    contact_info = (
        "Anywhere TX ♦ (123) 456-7890 ♦ "
        "<link href='mailto:johndoe@example.com'>johndoe@example.com</link> ♦ "
        "<link href='https://www.linkedin.com/in/johndoe/'>linkedin.com/in/johndoe</link> ♦ "
        "<link href='https://github.com/johndoe'>github.com/johndoe</link>"
    )
    elements.append(Paragraph(contact_info, contact_style))
    elements.append(Spacer(1, 0.2 * inch))

    # Professional Summary
    elements.append(Paragraph("PROFESSIONAL SUMMARY", subtitle_style))
    professional_summary = (
        "Experienced Data Engineer with a passion for building efficient data pipelines and optimizing data workflows. "
        "Proficient in SQL Server, Python, and various data visualization tools. Committed to continuous learning and professional growth."
    )
    elements.append(Paragraph(professional_summary, profile_style))
    elements.append(Spacer(1, 0.2 * inch))

    # Technical Skills
    elements.append(Paragraph("TECHNICAL SKILLS", subtitle_style))
    skills = (
        "• ETL/Data Integration: Alteryx, SSIS<br/>"
        "• Programming Languages: Python, PL/SQL<br/>"
        "• Cloud Platforms: Azure, AWS<br/>"
        "• DevOps Tools: GitHub, Git, CI/CD<br/>"
        "• APIs and Data Formats: RESTful APIs, XML, JSON, SOAP<br/>"
        "• Data Analysis & Modeling: NumPy, Pandas, scikit-learn, TensorFlow<br/>"
        "• Databases: Oracle, MySQL, SQL Server<br/>"
        "• Data Visualization: Power BI, Tableau, Python"
    )
    elements.append(Paragraph(skills, normal_style))
    elements.append(Spacer(1, 0.2 * inch))

    # Professional Experience
    elements.append(Paragraph("EXPERIENCE", subtitle_style))

    # Experience details
    experiences = [
        {
            "title": "Data Engineer",
            "company": "TechCorp - Remote | Jan 2020 - Present",
            "details": (
                "• Built data pipelines with SQL Server and Python.<br/>"
                "• Transformed and optimized data for reporting.<br/>"
                "• Automated workflows to enhance productivity."
            )
        },
        {
            "title": "Data Analyst",
            "company": "DataWorks - Remote | Jun 2015 - Dec 2019",
            "details": (
                "• Ingested data from flat files, APIs, and databases into SQL Server.<br/>"
                "• Developed stored procedures for data validation.<br/>"
                "• Created Power BI reports for various departments."
            )
        }
    ]

    for exp in experiences:
        elements.append(Paragraph(exp["title"], subtitle_style))
        elements.append(Paragraph(exp["company"], normal_style))
        elements.append(Paragraph(exp["details"], normal_style))
        elements.append(Spacer(1, 0.2 * inch))

    # Education
    elements.append(Paragraph("EDUCATION", subtitle_style))
    education = "B.S. in Computer Science<br/>University of State"
    elements.append(Paragraph(education, normal_style))
    elements.append(Spacer(1, 0.2 * inch))

    # Professional Competencies
    elements.append(Paragraph("PROFESSIONAL COMPETENCIES", subtitle_style))
    competencies = (
        "• Demonstrating Initiative<br/>"
        "• Communicating Effectively<br/>"
        "• Using Computers and Technology<br/>"
        "• Driving for Results"
    )
    elements.append(Paragraph(competencies, normal_style))
    
    # Build the PDF
    doc.build(elements) 
    pdf_output_path = "John_Doe_Resume.pdf"
    create_pdf(pdf_output_path)
    pdf_output_path
    
## Running the Code
Save the script and run it to generate your resume PDF. You’ll find your sleek new resume ready to impress potential employers.

## Conclusion
Creating a professional resume with Python is not only efficient but also showcases your technical skills. By using the reportlab library, you can generate a well-organized and polished resume that stands out. Whether you're a seasoned data engineer or just starting out, this guide can help you put your best foot forward.

Feel free to customize the placeholders and add more personal touches to make this resume truly yours. Happy coding!

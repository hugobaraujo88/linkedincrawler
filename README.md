# Project: Linkedin Crawler

## Context

This project was developed during my work at a Search Fund, a niche in the private equity sector. Search funds usually lack the resources to find companies available for acquisition in a proprietary way. Therefore, the search for "leads" (such as company owners or directors) was often done manually and non-systematically.

My idea was to create a way to systematize lead searching using a web scraping tool. This tool allowed for centralized contact searching on LinkedIn, systematization, and partial automation of the process. The result was a significant increase in productivity since I was able to obtain over 200 leads in just a few weeks, which would normally take months if done manually..

## Observações

The tool doesn't have a user-friendly interface because the goal was to put it into operation as quickly as possible. At the time, I was also learning to program in Python. However, the goal was achieved.

Currently, I believe that LinkedIn has implemented security filters, making it impossible or extremely difficult to scrape its pages.

Certainly, had I known more about Python and programming, I would have made numerous improvements to the code. However, I chose to keep the original version to demonstrate how I used technology to solve a real problem:

1. Problem Understanding: We needed more leads to increase the probability of acquisition.

2. Data Understanding: Where is the data, in what format (unstructured, web pages)?

3. Data Preparation: Preparing the data for entry into an Excel spreadsheet.

4. Evaluation and Application: Executing the algorithm to obtain the intended result and creating documentation/instructions.

## Instruções para usar o código

At the time, I wrote a set of instructions so that others could use the code:

1. In the "projects" folder on your desktop, copy and paste the Excel file "Linkedin_Crawler.xlsx" (which is on the driver).

2. Download the "Linkedin_Crawler.py" file and place it in the same folder as the Excel file.

3. Open Intellij IDEA and open the "Linkedin_Crawler.py" code.

4. Edit the parts in green with your LinkedIn login and password as shown in the image below. Be careful not to remove the double quotes.

![UsuarioSenha](https://raw.githubusercontent.com/hugobaraujo88/linkedincrawler/main/img/UsuarioSenha.png)

5)	After making these modifications, simply run the program.

Attention:

•	The Excel file must be closed during program execution (if it's open, Intellij IDEA will indicate an error).

•	The Python program will write to the first sheet of the Excel file, so I suggest leaving it configured as is. After using it for the first search, copy and paste it into another sheet, and always keep the "List" sheet clear and at the top.

![planilha](https://raw.githubusercontent.com/hugobaraujo88/linkedincrawler/main/img/planilha.png)

•	The program works because I tested it several times, but LinkedIn can change its internal parameters at any time.

•	If you want to change the search criteria for company partners/owners, simply modify line 172. The default is CEO OR DIRECTOR OR DIRECTRESS:

![url_emp](https://raw.githubusercontent.com/hugobaraujo88/linkedincrawler/main/img/url_emp.png)

It needs to be changed after the "=" and before "&origin". For example, if you want to use "partner" instead of CEO, the line would be:

'&keywords=(partner)%20OR%20(director)%20OR%20(directress)&origin=GLOBAL_SEARCH_HEADER'

Until recently, LinkedIn allowed up to 15 items for searching! But recently, it changed to only 3, unfortunately. If you want to add more search criteria, it would look like this:

'&keywords=(partner) %20OR20%(CEO)%20OR%20(director)%20OR%20(directress)&origin=GLOBAL_SEARCH_HEADER'

(searching for partner OR CEO OR director OR directress, 4 criteria). Just enclose the criteria in parentheses and add the expression %20OR%20 after, concatenating the various criteria (if LinkedIn allows it again...).

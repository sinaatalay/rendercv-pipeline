<!-- Remove below in src/markdown/Header.j2.md not in README.md -->

# RenderCV Pipeline

Are you ready to revolutionize the way you manage and craft your CVs and resumes?

Picture this:

1.  You simply update your `src/John_Doe_CV.yaml` input file and push the changes.
2.  Then, a pipeline generates a new PDF and Markdown from it and uploads it to the repository.
3.  When you are done with your work, you can create a new release on GitHub, tagging your CV with something like `v2024.04`. The pipeline will automatically add the PDF and its $\LaTeX$ source as assets to the release.
4.  You have successfully created your CV pipeline, and all the history is in safe hands and reproducible.

**How to start?**

1.  [Click here](https://github.com/new?template_name=rendercv-pipeline&template_owner=sinaatalay) to create your CV repository based on this `rendercv-pipeline` template repository.
2.  Edit either
    -  the `src/John_Doe_CV.yaml` file, or
    -  the contents of `src/markdown` or `src/classic` directories
    
    and push. Then, see the magic happen.

**Some tips**

1.  Learn more about [RenderCV](https://github.com/sinaatalay/rendercv) to understand what you can do with this tool.
2.  Edit and preview your CV in your browser without installing anything by creating a codespace. Click the <> **Code** button, then click the **Codespaces** tab, and then click **Create codespace on main**. The environment will be ready for RenderCV usage.
3.  Update `.vscode/launch.json` to point to your YAML file and press `F5` to run RenderCV in the browser.

<!-- Remove above in src/markdown/Header.j2.md not in README.md -->
# <<cv.name>>'s CV

((* if cv.phone *))
- Phone: <<cv.phone|replace("tel:", "")|replace("-"," ")>>
((* endif *))
((* if cv.email *))
- Email: [<<cv.email>>](mailto:<<cv.email>>)
((* endif *))
((* if cv.location *))
- Location: <<cv.location>>
((* endif *))
((* if cv.website *))
- Website: [<<cv.website|replace("https://","")|replace("/","")>>](<<cv.website>>)
((* endif *))
((* if cv.social_networks *))
    ((* for network in cv.social_networks *))
- <<network.network>>: [<<network.username>>](<<network.url>>)
    ((* endfor *))
((* endif *))

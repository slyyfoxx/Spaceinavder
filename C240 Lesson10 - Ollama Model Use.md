# How-to: Use Ollama Models in VSCode Chat

*Written: 16 May 2026*

> [!WARNING]
> Ollama and VS Code change often. Some steps, menu names or models may have changed since this how-to was written.

:rotating_light: **You do not need to use this worksheet unless** ...

- You cannot use GitHub Education models **or**
- You would like to try Ollama models **or**
- You have run out of the Github Education/Free Github tier model use



#### How to use Ollama Models for Free in VSCode Chat 

:rotating_light: **Warning**: Not all Ollama models are free. Even free models have usage limits.

Please follow the steps below, including re-installation of Ollama (even if you only did if a few weeks ago).

1. Reinstall Ollama to get the latest version. Reinstalling Ollama is the supported method to upgrade Ollama on Windows11. Go here: https://ollama.com/, find the Download button, **download ollama** and **reinstall** **ollama**.
2. Start a powershell terminal: Win + S and type '**powershell**'
3. Using the powershell terminal, ensure `ollama --version` gives you a response
4. enter `ollama launch vscode`
5. Select a model like `gemma4:31b-cloud`

![image-20260516124906794](C:\Users\peter_kenny\AppData\Roaming\Typora\typora-user-images\image-20260516124906794.png)

6. VSCode will pull the manifest and install it in VSCode. Then VSCode will start.

7. In VSCode, open the Chat window, click on Auto > then on the Gear Icon on the top right

   

![image-20260516125254313](C:\Users\peter_kenny\AppData\Roaming\Typora\typora-user-images\image-20260516125254313.png)

8. Ensure the model you selected in step 5 is present. Then dismiss the window.

![image-20260516125503636](C:\Users\peter_kenny\AppData\Roaming\Typora\typora-user-images\image-20260516125503636.png)

9. Go back to Auto > Other Models > and select the same model you selected in step 5.

![image-20260516125725132](C:\Users\peter_kenny\AppData\Roaming\Typora\typora-user-images\image-20260516125725132.png)

10. You are now using Ollama models in VSCode :)

![image-20260516130445143](C:\Users\peter_kenny\AppData\Roaming\Typora\typora-user-images\image-20260516130445143.png)
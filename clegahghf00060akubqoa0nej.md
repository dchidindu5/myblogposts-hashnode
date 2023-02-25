# Getting Started with Wagtail: A Beginner's Installation Guide


### **What is wagtail?**

Wagtail is an open-source content management system built on Django, It's focused on user experience, and offers precise control for designers and developers.

### **How to install Wagtail on Windows Operating System**

This guide is recommended for new users using

* Windows 11
    
* Windows 10
    
* Windows 8.1 pro
    
* Windows 8.1
    
* Windows 8.1 Enterprise
    
* Windows 8.0.
    

**Note** that the guide was written based on the experience gotten from Windows 8.1 operating system.

Let’s get started!!

### **Prerequisites**

- Command prompt interface
    
- Python
    
- PiP
    
- Pillow package
    
- Wagtail and its dependencies.
    


- **Install Python,**  [**Recommended(Python 3.10. 8)**](https://www.python.org/downloads/) (I installed python 3.10.0 on my PC).
    

After the installation verify that python has been successfully installed by typing the following in your **command prompt** `python –-version`  OR  `python -V`

![](https://lh4.googleusercontent.com/oedzk4TfBe79Ju9XYvwoS_b5gc4uR20quD-M0hMdH0ZaYmjMSRYr--jC4RvnjxMKbYZuncV0myRgrFqDOPrhLLRwiI-OMeXNHfNRlcmc61w92ZwATI2KanF1aczpGR3_PsfwBzp7uo3cKdoGKXW632M align="left")

**N/B** - If it generates an error, quickly add python path to the Environment Variables.

2. Install **Pip** (pip is automatically installed if you're using Python downloaded from its official Website But try to check the version before proceeding by using this command in your **command prompt**   `pip -V` **)**
    

![](https://lh4.googleusercontent.com/u8PM_Vr2KZOwbWYq5SDhHH0Ho9RBR0CgI9MIOJYoFM56N4MLgaFtltFEhcOMIZ0OBScaEbetxeqFbkHldPWDrthnJTJ9JO9JRMp9ZE8EO-SgqsMTcH-EB-MCsipaMIvzQCzs16m7UhcEZBxwjV4kaHM align="left")

If it generates an error, visit the official website [(pip installation)](https://pip.pypa.io/en/stable/installation/) and follow the instructions there.

3. Install **Pillow** package
    
Still, on your command prompt window type `pip install Pillow`

If you already have Pillow installed and you want to upgrade it use this

`pip install --upgrade Pillow`

![](https://lh6.googleusercontent.com/E87ibB33KWGAA31zRd9io8KVYx3e_KML4xuxpvPNKgnNtBnSsLrQ2CAY89thHKXI4XvDZ7ZT6JRFdFiksHad5DAel5A_lvoQ6eImykPCY46H0EefOYKlMtNO_i6ERkHAmDsUFROq3VaLkomPLzshn7g align="left")

4. **Create and activate a virtual environment**
    

For this tutorial, we will be using `venv` because it’s used for creating lightweight virtual environments.

Creating the environment is done by executing the following command on the cmd.exe    `python -m venv outreachywag\env`

I chose the name “outreachywag” you can as well use a different name for your virtual environment.

Followed by this command to activate the virtual environment

c:`\Users\YOUR PC NAME\outreachywag\env\Scripts\activate.bat`

![](https://lh3.googleusercontent.com/VJzkm-9XRVvt68QEIpwYBpNJgUCjh24s4mSl2uJgj7LFKXTvXIWScWZSW8BSiTVI9qr_4pr2vLCazjULlFTKrn6EoM0JuEDyHL1Id97bXFpWkV5NWLTyH5DLCt1ECpOFNEZKe0IMuucKKh7UeH395W0 align="left")

After that, you’ll have to open a new command window before proceeding to the next step.

5. **Finally, Install Wagtail**
    
Install wagtail using the pip command `pip install wagtail`

To effectively create a folder and site with wagtail dependencies  use the following commands=&gt;  `wagtail start outreachywag outreachywag`

> **N/B: Use the name you created earlier in step 4.**

6. **Install project dependencies**
    
`cd outreachywag`

`pip install -r requirements.txt`

Wait till it installs.

7. **Create a Database**
    

`python` [`manage.py`](http://manage.py) `migrate`

![](https://lh5.googleusercontent.com/aVuYr9W6B1J4eiGQNqEHoQ8SzCrvtksc5j87a0IjUNvmfw3HlZyp3_uS2KBXxlyKiw915vMqDjpIKVk0o1Zo-SssrUJ0QivKu4LSK9DOKT72FKd0TwyfUCafdPCEZkQvZYaB0FiLkq4QJny2x0fR8EE align="left")

8. **Create an Admin user**
    

`python` [`manage.py`](http://manage.py) `createsuperuser`

![](https://lh4.googleusercontent.com/Wz_HA338xWjIkw4HWtj-jsISfl80FkDgGI2m9J53yUWlm9HSFn188giEZv1ZafjiWGa4FeoDaLR66UMElyKQgnMhDxeGX4W0YcNNfvTNrUiHEiDOvd__tZYdDcfnev6z_ig4gQTRIWwHJ8a1U_uQhwQ align="left")

After executing the command, you will be required to put your credentials such as Username, Email and password.

While typing the password, it will remain unseen by the user but keep typing and use a short and secure phrase for the password.

9. **Start the server**
    

To start up the server, run the command below to get started

`python` [`manage.py`](http://manage.py) `runserver`

![](https://lh5.googleusercontent.com/wSusBlEAeyq4uXd5Ii-CdPg6HW-4zk0HMfn6Quikz9YvvvXRNBjoyWft62C8iQ-7Vq4yplZ6v6wuKFN9Vqiq0NnjLybGi9Z54iDFz2gO2pTT6BBjnqXbHlLbdAl1PvWGfrybwzKgDv0sWaQOzDpjw3A align="left")

If it runs successfully,Open your browser and enter this address, [http://127.0.0.1:8000](http://127.0.0.1:8000) it will show you a welcome page as shown below.

![](https://lh6.googleusercontent.com/wnIUHXWxMDPBWtLim0GUc35pqK4PzJbTljXrHX2IVL-cVdCFH0mKjmzmdgUGJgYXDM8iDLipbMior26NcX_m6s7K_0UifuwH4e3fXtzwyb0HTwy4qFMHJQcCnaX8Xa6ar8teLVMgDDF33SVyVw2YqjQ align="left")

10. Additionally, navigate to [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin) to access the administrator area.
    

You will be asked for a username and password that you created in **step 9**.

11. You've successfully installed wagtail and its dependencies!!.
    

## Conclusion

This tutorial walked you through installing the open-source Wagtail CMS into your windows operating system. To learn more about installation into other operating systems, customising wagtail and wagtail APIs, visit [https://docs.wagtail.org/en/stable/](https://docs.wagtail.org/en/stable/)


### Sources

* [Wagtail](https://wagtail.org)
    
* [Caktus](https://www.caktusgroup.com/blog/2019/03/07/why-we-love-wagtail/)
    
* [Django CMS](https://www.django-cms.org/en/blog/2021/02/03/django-cms-vs-wagtail-which-cms-is-best-for-your-website/)
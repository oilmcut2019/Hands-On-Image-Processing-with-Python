## Creating Virtual-environment using PIP Ubuntu

---

if you want to creating virtual-environment using pip, you can following guideline bellow this

1. install virtualenv in python3

   $ python3 -m pip install --user virtualenv

2. On Debian/Ubuntu systems, you need to install the python3-venv package because ensurepip is not
   available following command

   $ apt-get install python3-venv

3. create environment following command 

   $ python3 -m venv brightness-project

4. for activate the env use command

   $ source brightness-project/bin/activate

5. for deactivate the virtual env, use command

   $ deactivate 

6. installing packages

   $ pip install [name packages] 

7. freezing dependencies to show a list of package specifiers, use command

   $ pip freeze
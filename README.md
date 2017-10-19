# Exercises:

The exercises are built on top of each other which means you need to e.g. finish exercise one before you can start working on exercise two.
If you stuck with one exercise you can look at the linked answer.
We will use the OBS reference installation on [build.opensuse.org](https://build.opensuse.org) which requires you to create an account.

1. Create a GitHub repository with a simple script in it, which prints ``Hello World`` to the console
      * [Answer](answers/exercise-1)

2. Create a package in your [build.opensuse.org](https://build.opensuse.org) home project

3. The package should contain a spec file which installs your ``Hello World`` script to ``/bin``
      * https://en.opensuse.org/openSUSE:Build_Service_Tutorial
      * [Answer](answers/exercise-3)
      * Bonus task: Make the package build for various distributions and architectures

4. The package should contain a ``_service`` file, which fetches the sources from the GitHub repository you've created in the previous step
      * https://en.opensuse.org/openSUSE:Build_Service_Concept_SourceService
      * [Answer](answers/exercise-4)

5. Connect your GitHub repository with OBS to let GitHub trigger a package build, whenever a new commit has been pushed to master
      * You can create a security token with `osc token`
      * You can install `osc` for various distributions from this [repository](http://download.opensuse.org/repositories/openSUSE:/Tools/) 
      * You can add a GitHub webhook in your repository via ``Settings -> Integrations & services``

6. Create a new appliance from a template on [build.opensuse.org](https://build.opensuse.org/image_templates)
      * There is an Open Source Summit example template, select this one

7. Add your ``Hello World`` package to the appliance
      * Either use the kiwi image editor view (``Edit Kiwi``) or edit the ``kiwi.xml`` file
      * You need to add your ``home`` project repository and the ``Hello World`` package to your appliance
      * https://doc.opensuse.org/projects/kiwi/doc/#sec.description.repository
      * https://doc.opensuse.org/projects/kiwi/doc/#sec.description.packages
      * [Answer](answers/exercise-7)

8. Add a ``root`` and a ``tux`` user to your appliance
      * https://doc.opensuse.org/projects/kiwi/doc/#sec.description.users
      * [Answer](answers/exercise-8)

9. Add the ``apache2`` package and make sure that apache gets started automatically
      * You can enable services in the `config.sh` script
      * You can start the apache2 webserver via ``systemctl enable apache2``
      * https://doc.opensuse.org/projects/kiwi/doc/#ref.kiwi.config.sh
      * [Answer](answers/exercise-9)

10. Add a simple ``Hello World`` html file to your apache2 webserver
      * Kiwi uses a directory called ``root`` to store the root tree of your new image. Add your files in a directory named ``root``.
      * The root directory needs to be archived as tar.gz file (``tar -zcvf tar-archive-name.tar.gz source-folder-name``)
      * The html files need to go into ``/srv/www/htdocs``
      * [Answer](answers/exercise-11)

13. Bonus task: Download and run your appliance with QEMU / VirtualBox and test, if everything works as expected

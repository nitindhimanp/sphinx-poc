.. lnp-docu documentation master file, created by
   sphinx-quickstart on Wed Jul 12 14:19:10 2023.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Getting Started with Teacher Audit Portal Frontend documentation!
=================================================================
Clone Repository
----------------

To clone Teacher Audit Portal frontend Project, run the following command from the command line:

.. code-block:: bash

   git clone https://github.com/AssessEd/lnp-live-class-frontend.git

| The latest prod branch is ``dashboard2_demo_2``,
| while the latest branch dev branch is ``liveclass_dev``.
| Also this repo hosts the GPT Audit Portal on the ``poc/gpt-audit`` branch.


Installation
----------------

To install the packages , use the following command :

.. code-block:: bash

   npm i

OR if the above command gives dependency mismatch run the following command

.. code-block:: bash

   npm i -force

The project has been tested and works well with Node version ``v16.x.x`` and above.

Serving the Documentation
-------------------------

To run the project, use the following command :

.. code-block:: bash

   npm run start

which, being a react project, by default runs on port ``3000``, so the frontend server should now be accessible at ``http://localhost:3000/``

Credential Dependencies
-----------------------


- Git Branches : 
   | Prod : ``dashboard2_demo_2`` ( port : ``3001`` )
   | Dev : ``liveclass_dev`` ( port : ``3002``)
   | GPT Audit Portal : ``poc/gpt-audit`` ( port : ``3002`` , different path)

   | `Note : Port have been set in .env file`

- Deployment Process

   For the deployement on the Prod environment: 

   .. code-block:: bash

      sudo ssh -i liveclassFEMachine.pem ubuntu@52.6.96.45
      cd jeeva
         
      
   For the deployement on the Dev environment :

   .. code-block:: bash

      sudo ssh -i liveclassdev.pem ubuntu@13.127.87.134
      cd liveclassdevFE

   For the deployement of the GPT Audit Portal :

   .. code-block:: bash

      sudo ssh -i liveclassdev.pem ubuntu@13.127.87.134
      cd gpt-audit-portal

   The above mentioned frontend servers have been deployed as ``pm2`` instances. Following are the commands of ``pm2`` to run frontend servers as its instances.

   .. code-block:: bash

      sudo npm install pm2@latest -g  [ only once for pm2 installation]
      pm2 start npm --name “live class” -- start

   To manage the ``pm2`` instances following commands can be used :

   .. code-block:: bash

      pm2 ls
      pm2 stop <pm2_instance_id>
      pm2 delete <pm2_instance_id>


- URLs :
   | Dev : ``http://13.127.87.134:3002/videos``
   | Prod : ``https://teacher-audit.byjusweb.com/videos``  ``[http://52.6.96.45:3000/videos]``
   | GPT Audit Portal : ``http://13.127.87.134:3002/gpt-video-audits``


----------------


Overview
======================================================

The Tecaher Audit Portal frontend is a GUI using which the auditors can easily analyse the classroom videos of teachers coming from 
various sources like WHJ, Neo, BTC, etc. Not only does it provide a platform for the auditors to manually analyse the video, 
but also submit their feedbacks on a certain set of questions and can also add remarks to those answered questions. 

Along with providing the auditors with the above mentioned functionality, the portal also presents the Audit data for each video 
coming from the ML Analysis for the various parameters which correspond to above mentioned question set.

The dashboard also shows the video player with the actual video being audited and a interactive chart with the graph data of 
various parameters from ML analysis over the length of the video. The graph lines can be clicked at any point, which takes the 
user to that point in video where that analysis was captured.

The intial page of the portal presents a list of all the videos which have either been audited or are ready to audited by the 
manual auditors. For each video in the list there are certain preview icon linked to the ML analysis parameters for that video, 
which gives the user an idea of what to expect from the audit report of the particular video.


.. toctree::
   :maxdepth: 2
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

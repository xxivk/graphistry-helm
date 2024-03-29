.. This page has been autogenerated using Frigate.
   https://frigate.readthedocs.io

Morpheus-ai-engine
======================

A Helm chart for deploying the NVIDIA Morpheus AI Engine which includes the Triton Inference Server.


Install Nvidia Morpheus
---------------------------------------------------
**NOTE:** Morpheus AI Engine requires you sign up for an NGC api key, you can sign up here for an api key: `Nvidia NGC <https://ngc.nvidia.com/signin>`_ 


  .. tabs::

    .. tab:: Local from Source
      .. code-block:: shell-session            
                
        git clone https://github.com/graphistry/graphistry-helm && cd graphistry-helm
        helm upgrade -i morpheus ./charts/morpheus-ai-engine --namespace morpheus --create-namespace 


    .. tab:: From Graphistry Helm Repo
      .. code-block:: shell-session            
                
        helm repo add graphistry-helm https://graphistry.github.io/graphistry-helm/
        helm upgrade -i morpheus graphistry-helm/morpheus-ai-engine --namespace morpheus --create-namespace 


Configuration
-------------

The following table lists the configurable parameters of the Morpheus-ai-engine chart and their default values.

================================================== ==================================================================================================== ==================================================
Parameter                                          Description                                                                                          Default
================================================== ==================================================================================================== ==================================================
``replicaCount``                                                                                                                                        ``1``                                             
``ngc.username``                                                                                                                                        ``"$oauthtoken"``                                 
``ngc.apiKey``                                                                                                                                          ``""``                                            
``ngc.org``                                                                                                                                             ``""``                                            
``ngc.team``                                                                                                                                            ``""``                                            
``aiengine.registry``                                                                                                                                   ``"nvcr.io/nvidia"``                              
``aiengine.image``                                                                                                                                      ``"tritonserver"``                                
``aiengine.version``                                                                                                                                    ``"22.06-py3"``                                   
``aiengine.args``                                                                                                                                       ``["tritonserver", "--model-repository", "/common/triton-model-repo", "--model-control-mode", "explicit"]``
``aiengine.resources.limits.nvidia.com/gpu``                                                                                                            ``1``                                             
``broker.registry``                                                                                                                                     ``"docker.io"``                                   
``broker.image``                                                                                                                                        ``"bitnami/kafka"``                               
``broker.version``                                                                                                                                      ``"2.7.0"``                                       
``broker.brokerPort``                                                                                                                                   ``30092``                                         
``zookeeper.registry``                                                                                                                                  ``"docker.io"``                                   
``zookeeper.image``                                                                                                                                     ``"zookeeper"``                                   
``zookeeper.version``                                                                                                                                   ``"3.6.3"``                                       
``hostCommonPath``                                                                                                                                      ``"/opt/morpheus/common"``                        
``imagePullPolicy``                                                                                                                                     ``"IfNotPresent"``                                
``imagePullSecrets``                                                                                                                                    ``[{"name": "nvidia-registrykey-secret"}]``       
``serviceAccount.create``                                                                                                                               ``false``                                         
``serviceAccount.name``                                                                                                                                 ``"morpheus"``                                    
``platform.openshift``                                                                                                                                  ``false``                                         
``loadBalancer.enabled``                                                                                                                                ``false``                                         
``nodeSelector``                                                                                                                                        ``{}``                                            
================================================== ==================================================================================================== ==================================================


For more information on NVIDIA Morpheus, visit the Morpheus documentation: `NVIDIA Morpheus Documentation <https://docs.nvidia.com/morpheus/index.html>`_ 






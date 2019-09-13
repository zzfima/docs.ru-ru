---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: 0d77af319e18868ce7d600269cd9afaa0c4ce2c6
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928647"
---
# <a name="customchannelstester"></a>CustomChannelsTester
`CustomChannelsTester` - это средство, позволяющее проверять реализации пользовательских каналов на соответствие набору предопределенных контрактов службы. Можно выбрать набор контрактов службы и передать его средству с помощью XML-файла. Затем средство создает службу и клиента, использующих реализации пользовательского канала во время обмена сообщениями.  
  
### <a name="to-build-the-tool"></a>Построение средства  
  
1. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. При построении решения создаются три файла: Кустомчаннелстестер. exe, Тестспек. XML и Самплерун. cmd. Файл самплерун. cmd содержит образец командной строки, который показывает, как использовать это средство для тестирования [транспорта. Пример](../../../../docs/framework/wcf/samples/transport-udp.md) протокола UDP.  
  
### <a name="to-run-the-tool"></a>Запуск средства  
  
- В командной строке введите следующую команду.  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     Необходимо использовать параметр `/binding`.  
  
     `/dll`требуется, если "Binding" не является предоставляемой системой привязкой, предоставляемой Windows Communication Foundation (WCF).  
  
     Параметр `/testspec` является необязательным.  
  
     В результате создаются сервер и клиенты на основе спецификаций теста и привязки.  
  
     Выполняет клиент и сервер и возвращает результаты.  
  
     Далее приведен пример XML-кода для описания спецификаций теста (testspec.xml).  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the client. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  

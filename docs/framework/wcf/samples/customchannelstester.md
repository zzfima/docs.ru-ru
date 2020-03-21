---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: c23bd3eddd49972b7083347fed88d4e70707ae58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183808"
---
# <a name="customchannelstester"></a>CustomChannelsTester
`CustomChannelsTester` - это средство, позволяющее проверять реализации пользовательских каналов на соответствие набору предопределенных контрактов службы. Можно выбрать набор контрактов службы и передать его средству с помощью XML-файла. Затем средство создает службу и клиента, использующих реализации пользовательского канала во время обмена сообщениями.  
  
### <a name="to-build-the-tool"></a>Построение средства  
  
1. Чтобы создать решение, следуйте инструкциям по [созданию образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
2. При построении решения создаются три файла: CustomChannelsTester.exe, TestSpec.xml и SampleRun.cmd. Файл SampleRun.cmd имеет пример командной строки, которая показывает, как использовать этот инструмент для [тестирования транспорта:](../../../../docs/framework/wcf/samples/transport-udp.md) образец UDP.  
  
### <a name="to-run-the-tool"></a>Запуск средства  
  
- В командной строке введите следующую команду.  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     Необходимо использовать параметр `/binding`.  
  
     `/dll`требуется, если "обязательный" не является системной привязкой, предоставленной Фондом связи Windows (WCF).  
  
     Аргумент `/testspec` является необязательным.  
  
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

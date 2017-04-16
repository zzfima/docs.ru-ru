---
title: "ConfigurationCodeGenerator | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# ConfigurationCodeGenerator
ConfigurationCodeGenerator — это средство, позволяющее предоставлять системе конфигурации реализации пользовательских каналов.Это позволяет пользователям пользовательских каналов настраивать каналы с помощью файла конфигурации, как это происходит в случае с системными привязками, например `NetTcpBinding`, или пользовательскими привязками с помощью элемента `TcpTransportBindingElement`.  
  
 При разработке пользовательского канала и его предоставлении в модели программирования с помощью нового элемента `BindingElement` или `Binding` необходимо создать набор классов, чтобы `BindingElement` или `Binding` можно было настраивать с помощью файла конфигурации.Средство ConfigurationCodeGenerator позволяет создать эти классы и сделать работу пользователей более удобной.  
  
### Построение средства  
  
1.  Чтобы выполнить построение решения, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  В результате построения решения формируется один файл: ConfigurationCodeGenerator.exe.В файле SampleRun.cmd содержится пример командной строки, показывающий использование этого средства для формирования классов для образца [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
### Запуск средства  
  
1.  В командной строке введите следующую команду, если имеется пользовательский тип `BindingElement` и пользовательский тип `Binding`:  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
  
    ```  
  
     Либо введите следующую команду, если имеется только пользовательский тип `BindingElement`:  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
  
    ```  
  
     Либо введите следующую команду, если имеется только пользовательский тип `Binding`:  
  
    ```  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
  
    ```  
  
     Команда создает три файла CS для элемента `BindingElement` \(если задан параметр \/be:\), пять файлов CS для стандартного элемента `Binding` \(если задан параметр \/sb:\), а также XML\-файл.  
  
    1.  Если используется параметр \/be, один из файлов CS реализует `BindingElementExtensionSection` для элемента привязки.Этот код предоставляет элемент `BindingElement` для системы конфигурации, чтобы элементом привязки могли пользоваться другие пользовательские привязки.В других файлах содержатся классы, представляющие значения по умолчанию и константы.В файлах имеются комментарии `//TODO` напоминающие разработчикам о необходимости обновить значения по умолчанию.  
  
    2.  Если задан параметр \/sb, два файла CS реализуют элементы `StandardBindingElement` и `StandardBindingCollectionElement` соответственно, в результате чего стандартная привязка предоставляется системе конфигурации.В других файлах содержатся классы, представляющие значения по умолчанию и константы.В файлах имеются комментарии `//TODO` напоминающие разработчикам о необходимости обновить значения по умолчанию.  
  
         Если задан параметр \/sb:, в файле CodeToAddTo\<*YourStdBinding*\>.cs содержится код, который необходимо вручную добавить в класс, реализующий стандартную привязку.  
  
     Файл SampleConfig.xml file содержит код конфигурации, который необходимо добавить в файл конфигурации, регистрирующий обработчики, определенные ранее на шагах 1 и 2.  
  
## См. также
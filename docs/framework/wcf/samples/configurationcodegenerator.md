---
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: a01300024f89a0a189045d80622121f7db739a39
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912415"
---
# <a name="configurationcodegenerator"></a>ConfigurationCodeGenerator
ConfigurationCodeGenerator - это средство, позволяющее предоставлять системе конфигурации реализации пользовательских каналов. Это позволяет пользователям пользовательских каналов настраивать каналы с помощью файла конфигурации, как это происходит в случае с системными привязками, например `NetTcpBinding`, или пользовательскими привязками с помощью элемента `TcpTransportBindingElement`.  
  
 При разработке пользовательского канала и его предоставлении в модели программирования с помощью нового элемента `BindingElement` или `Binding` необходимо создать набор классов, чтобы `BindingElement` или `Binding` можно было настраивать с помощью файла конфигурации. Средство ConfigurationCodeGenerator позволяет создать эти классы и сделать работу пользователей более удобной.  
  
### <a name="to-build-the-tool"></a>Построение средства  
  
1. Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Построении решения создается один файл: ConfigurationCodeGenerator.exe. В файле SampleRun.cmd имеется пример командной строки, в котором показано, как использовать это средство для создания классов для [транспорта: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.  
  
### <a name="to-run-the-tool"></a>Запуск средства  
  
1. В командной строке введите следующую команду, если имеется пользовательский тип `BindingElement` и пользовательский тип `Binding`:  
  
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
  
     Команда создает три файла CS для элемента `BindingElement` (если задан параметр /be:), пять файлов CS для стандартного элемента `Binding` (если задан параметр /sb:), а также XML-файл.  
  
    1. Если используется параметр /be, один из файлов CS реализует `BindingElementExtensionSection` для элемента привязки. Этот код предоставляет элемент `BindingElement` для системы конфигурации, чтобы элементом привязки могли пользоваться другие пользовательские привязки. В других файлах содержатся классы, представляющие значения по умолчанию и константы. В файлах имеются комментарии `//TODO` напоминающие разработчикам о необходимости обновить значения по умолчанию.  
  
    2. Если задан параметр /sb, два файла CS реализуют элементы `StandardBindingElement` и `StandardBindingCollectionElement` соответственно, в результате чего стандартная привязка предоставляется системе конфигурации. В других файлах содержатся классы, представляющие значения по умолчанию и константы. В файлах имеются комментарии `//TODO` напоминающие разработчикам о необходимости обновить значения по умолчанию.  
  
         Если вы указали/SB: параметр в файле CodeToAddTo\<*YourStdBinding*> содержится код, который необходимо вручную добавить в класс, реализующий стандартную привязку.  
  
     Файл SampleConfig.xml file содержит код конфигурации, который необходимо добавить в файл конфигурации, регистрирующий обработчики, определенные ранее на шагах 1 и 2.  

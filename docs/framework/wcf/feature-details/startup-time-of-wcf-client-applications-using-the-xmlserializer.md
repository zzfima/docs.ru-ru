---
title: Практическое руководство. Сокращение времени запуска клиентских приложений WCF с использованием XmlSerializer
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: ca15d710a30586135f0d030e155b09b63a22ee45
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976060"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a>Практическое руководство. Сокращение времени запуска клиентских приложений WCF с использованием XmlSerializer
Службы и клиентские приложения, использующие типы данных, сериализуемые с помощью сериализатора <xref:System.Xml.Serialization.XmlSerializer>, создают и компилируют код сериализации для этих типов данных во время выполнения, что может привести к снижению производительности при запуске.  
  
> [!NOTE]
> Предварительно созданный код сериализации может использоваться только в клиентских приложениях, но не в службах.  
  
 [Средство служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) может улучшить производительность при запуске этих приложений, создавая необходимый код сериализации из скомпилированных сборок для приложения. Svcutil.exe создает код сериализации для всех типов данных, используемых в контрактах служб в скомпилированной сборке приложения, которые могут быть сериализованы с помощью <xref:System.Xml.Serialization.XmlSerializer>. Контракты служб и операций, предусматривающие использование <xref:System.Xml.Serialization.XmlSerializer>, отмечены атрибутом <xref:System.ServiceModel.XmlSerializerFormatAttribute>.  
  
### <a name="to-generate-xmlserializer-serialization-code"></a>Создание кода сериализации XmlSerializer  
  
1. Скомпилируйте код службы или клиента в одну или несколько сборок.  
  
2. Откройте окно командной строки SDK.  
  
3. Из командной строки запустите средство Svcutil.exe, используя следующий формат.  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     Аргумент `assemblyPath` задает путь к сборке, содержащей типы из контракта службы. Svcutil.exe создает код сериализации для всех типов данных, используемых в контрактах служб в скомпилированной сборке приложения, которые могут быть сериализованы с помощью <xref:System.Xml.Serialization.XmlSerializer>.  
  
     Svcutil.exe может формировать только код сериализации на C#. Для каждой входной сборки создается один файл исходного кода. Нельзя использовать параметр **/Language** для изменения языка созданного кода.  
  
     Чтобы указать путь к зависимым сборкам, используйте параметр **/Reference** .  
  
4. Предоставьте приложению доступ к созданному коду сериализации одним из следующих способов.  
  
    1. Скомпилируйте созданный код сериализации в отдельную сборку с именем [*Исходная сборка*]. XmlSerializer. dll (например, MyApp. XmlSerializers. dll). Приложение должно иметь возможность загрузить эту сборку, которая должна быть подписана с помощью того же ключа, что и исходная сборка. В случае повторной компиляции исходной сборки необходимо заново создать сборку сериализации.  
  
    2. Скомпилируйте созданный код сериализации в отдельную сборку и используйте атрибут <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> в контракте службы, в котором используется атрибут <xref:System.ServiceModel.XmlSerializerFormatAttribute>. Задайте свойство <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> или <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> так, чтобы оно указывало на скомпилированную сборку сериализации.  
  
    3. Скомпилируйте созданный код сериализации в сборку приложения и добавьте атрибут <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> в контракт службы, в котором используется атрибут <xref:System.ServiceModel.XmlSerializerFormatAttribute>. Не задавайте свойства <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> или <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>. По умолчанию предполагается, что сборка сериализации по умолчанию является текущей сборкой.  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a>Создание кода сериализации XmlSerializer в Visual Studio  
  
1. Создание проектов службы и клиента WCF в Visual Studio. Затем добавьте ссылку на службу в клиентский проект.  
  
2. Добавьте <xref:System.ServiceModel.XmlSerializerFormatAttribute> в контракт службы в файле *Reference.CS* в проекте клиентского приложения в разделе **укзать** -> **Reference. svcmap**. Обратите внимание, что для просмотра этих файлов необходимо показать все файлы в **Обозреватель решений** .  
  
3. Создайте клиентское приложение.  
  
4. Используйте [средство служебной программы для метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , чтобы создать предварительно созданный файл сериализатора *. CS* с помощью команды:  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     Аргумент _ указывает путь к клиентской сборке WCF.  
  
     Например:  
  
    ```console  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     Будет создан файл *WCFClient.XmlSerializers.dll.CS* .  
  
5. Скомпилируйте предварительно созданную сборку сериализации.  
  
     В зависимости от примера, приведенного на предыдущем шаге, команда Compile будет выглядеть следующим образом:  
  
    ```console  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     Убедитесь, что созданная *вкфклиент. XmlSerializer. dll* находится в том же каталоге, что и клиентское приложение, которое в данном случае является *вкфклиент. exe* .  
  
6. Запустите клиентское приложение обычным образом. Будет использоваться предварительно созданная сборка сериализации.  
  
## <a name="example"></a>Пример  
 Следующая команда создает типы сериализации для типов `XmlSerializer`, используемых любыми контрактами служб в сборке.  
  
```console  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a>См. также

- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)

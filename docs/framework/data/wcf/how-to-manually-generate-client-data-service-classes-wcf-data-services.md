---
title: Практическое руководство. Создание клиентских классов службы данных вручную (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: f8d99213a1ef98c48855ba9f561f87a800768c89
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894295"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>Практическое руководство. Создание клиентских классов службы данных вручную (WCF Data Services)
WCF Data Services интегрируется с Visual Studio, позволяя автоматически создавать классы клиентских служб данных при использовании диалогового окна **Добавление ссылки на службу** для добавления ссылки на службу данных в проекте Visual Studio. Дополнительные сведения см. в разделе [Практическое руководство. Добавьте ссылку](how-to-add-a-data-service-reference-wcf-data-services.md)на службу данных. Эти же клиентские классы службы данных можно сформировать и вручную с помощью программы для формирования кода `DataSvcUtil.exe`. Это средство, которое входит в состав WCF Data Services, создает классы .NET Framework из определения службы данных. Она также может использоваться для формирования классов службы данных из файла концептуальной модели (CSDL) и из файла EDMX, представляющего модель Entity Framework в проекте Visual Studio.

 Пример в этом разделе создает клиентские классы службы данных на основе образца службы данных Northwind. Эта служба создается при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md). Некоторые примеры в этом разделе требуют наличия файла концептуальной модели для модели Northwind. Дополнительные сведения см. в разделе [Практическое руководство. Используйте EdmGen. exe для создания файлов](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)модели и сопоставления. Некоторые примеры в этом разделе требуют наличия файла EDMX для модели Northwind. Дополнительные сведения см. в разделе [Общие сведения о файле EDMX](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).

### <a name="to-generate-c-classes-that-support-data-binding"></a>Формирование классов C#, поддерживающих привязку данных

- Выполните в командной строке следующую команду (введя ее без разрывов строк):

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a>Формирование классов Visual Basic, поддерживающих привязку данных

- Выполните в командной строке следующую команду (введя ее без разрывов строк):

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.

### <a name="to-generate-c-classes-based-on-the-service-uri"></a>Формирование классов C# на основе URI службы

- Выполните в командной строке следующую команду (введя ее без разрывов строк):

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a>Формирование классов Visual Basic на основе URI службы

- Выполните в командной строке следующую команду (введя ее без разрывов строк):

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a>Формирование классов C# на основе файла концептуальной модели (CSDL)

- Выполните в командной строке следующую команду (введя ее без разрывов строк):

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a>Формирование классов Visual Basic на основе файла концептуальной модели (CSDL)

- Выполните в командной строке следующую команду (введя ее без разрывов строк):

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a>Формирование классов C# на основе файла EDMX

- Выполните в командной строке следующую команду (введя ее без разрывов строк):

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a>Формирование классов Visual Basic на основе файла EDMX

- Выполните в командной строке следующую команду (введя ее без разрывов строк):

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a>См. также

- [Создание библиотеки клиентов службы данных](generating-the-data-service-client-library-wcf-data-services.md)
- [Практическое руководство. Добавить ссылку на службу данных](how-to-add-a-data-service-reference-wcf-data-services.md)
- [Служебная программа клиента службы данных WCF (DataSvcUtil.exe)](wcf-data-service-client-utility-datasvcutil-exe.md)

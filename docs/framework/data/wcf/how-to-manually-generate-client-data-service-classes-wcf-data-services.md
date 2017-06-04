---
title: "Как формировать клиентские классы службы данных вручную (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы WCF Data Services, клиентская библиотека"
  - "Службы WCF Data Services, настройка"
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Как формировать клиентские классы службы данных вручную (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] интегрируются с Visual Studio, позволяя автоматически сформировать клиентские классы службы данных с помощью диалогового окна **Добавление ссылки на службу** для добавления ссылки на службу данных в проект Visual Studio.  Для получения дополнительной информации см. [Как добавить ссылку на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  Можно также вручную создать те же клиентские классы службы данных с помощью средства создания кода `DataSvcUtil.exe`. Этот инструмент, входящий в [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], формирует классы .NET Framework из определения службы данных.  Она также может использоваться для формирования классов службы данных из файла концептуальной модели \(CSDL\) и из файла EDMX, представляющего модель Entity Framework в проекте Visual Studio.  
  
 Пример в этом разделе создает клиентские классы службы данных на основе образца службы данных Northwind.  Эта служба создается после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  Некоторые примеры в этом разделе требуют наличия файла концептуальной модели для модели Northwind.  Для получения дополнительной информации см. [Как использовать средство EdmGen.exe для создания файлов модели и сопоставления](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  Некоторые примеры в этом разделе требуют наличия файла EDMX для модели Northwind.  Для получения дополнительной информации см. [.edmx File Overview](http://msdn.microsoft.com/ru-ru/f4c8e7ce-1db6-417e-9759-15f8b55155d4).  
  
### Формирование классов C\#, поддерживающих привязку данных  
  
-   Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.  
  
### Формирование классов Visual Basic, поддерживающих привязку данных  
  
-   Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.  
  
### Формирование классов C\# на основе URI службы  
  
-   Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.  
  
### Формирование классов Visual Basic на основе URI службы  
  
-   Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.  
  
### Формирование классов C\# на основе файла концептуальной модели \(CSDL\)  
  
-   Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs  
    ```  
  
### Формирование классов Visual Basic на основе файла концептуальной модели \(CSDL\)  
  
-   Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb  
    ```  
  
### Формирование классов C\# на основе файла EDMX  
  
-   Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs   
    ```  
  
### Формирование классов Visual Basic на основе файла EDMX  
  
-   Выполните в командной строке следующую команду \(введя ее без разрывов строк\):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb   
    ```  
  
## См. также  
 [Формирование клиентской библиотеки службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)   
 [Как добавить ссылку на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)   
 [Клиентская программа служб WCF Data Services \(DataSvcUtil.exe\)](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
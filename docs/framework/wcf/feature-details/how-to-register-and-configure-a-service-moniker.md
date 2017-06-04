---
title: "Практическое руководство. Регистрация и настройка моникера службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "COM [WCF], настройка моникеров служб"
  - "COM [WCF], регистрация моникеров служб"
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Практическое руководство. Регистрация и настройка моникера службы
Перед использованием моникера службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в рамках приложения COM с типизированным контрактом необходимо зарегистрировать необходимые типы с атрибутами с помощью COM и настроить приложение COM и моникер в соответствии с необходимой конфигурацией привязки.  
  
### Регистрация необходимых типов с атрибутами с помощью COM  
  
1.  С помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) получите контракт метаданных службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  При этом будет создан исходный код сборки клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и файл конфигурации клиентского приложения.  
  
2.  Убедитесь, что все типы в сборке имеют пометку `ComVisible`.  Для этого добавьте в файл AssemblyInfo.cs в проекте Visual Studio следующий атрибут.  
  
    ```  
    [assembly: ComVisible(true)]  
    ```  
  
3.  Скомпилируйте управляемый клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в виде сборки со строгим именем.  Для этого нужно подписать ее с помощью пары ключей шифрования.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Подпись сборки строгим именем](http://go.microsoft.com/fwlink/?LinkId=94874) в руководстве разработчика по .NET.  
  
4.  С помощью средства регистрации сборок \(Regasm.exe\) с параметром `/tlb` зарегистрируйте типы сборки в COM.  
  
5.  Чтобы добавить сборку в глобальный кэш сборок, используйте средство глобального кэша сборок \(Gacutil.exe\).  
  
    > [!NOTE]
    >  Подписывание сборки и ее добавление в глобальный кэш сборок являются необязательными шагами, однако они могут упростить процесс загрузки сборки из правильного расположения во время выполнения.  
  
### Настройка приложения COM и моникера с использованием нужной конфигурации привязки  
  
-   Поместите определения привязки \(созданные средством [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) в созданном файле конфигурации клиентского приложения\) в файл конфигурации клиентского приложения.  Например, для исполняемого файла Visual Basic 6.0 с именем CallCenterClient.exe конфигурацию необходимо помещать в файл с именем CallCenterConfig.exe.config в том же каталоге, что и исполняемый файл.  Теперь клиентское приложение может использовать моникер.  Обратите внимание, что конфигурация привязки не требуется, если используется один из стандартных типов привязок [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
     Регистрируется следующий тип.  
  
    ```  
    using System.ServiceModel;  
  
    ...  
  
    [ServiceContract]   
    public interface IMathService   
    {  
    [OperationContract]  
    public int Add(int x, int y);  
    [OperationContract]  
    public int Subtract(int x, int y);  
    }  
    ```  
  
     Доступ к приложению предоставляется через следующую привязку `wsHttpBinding`.  Для заданного типа и конфигурации приложения используются следующие примеры строк моникера.  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1  
  
    ```  
  
     `or`  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}  
  
    ```  
  
     Можно использовать любую из этих строк моникера из приложения Visual Basic 6.0 после добавления ссылки на сборку, содержащую типы `IMathService`, как показано в следующем образце кода.  
  
    ```  
    Dim MathProxy As IMathService  
    Dim result As Integer  
  
    Set MathProxy = GetObject( _  
            "service4:address=http://localhost/MathService, _  
            binding=wsHttpBinding, _  
            bindingConfiguration=Binding1")  
  
    result = MathProxy.Add(3, 5)  
  
    ```  
  
     В этом примере определение конфигурации привязки `Binding1` хранится в файле конфигурации клиентского приложения с соответствующим именем, например vb6appname.exe.config.  
  
    > [!NOTE]
    >  Аналогичный код можно использовать в C\#, C\+\+ или любом другом языке приложений .NET.  
  
    > [!NOTE]
    >  Если моникер сформирован неправильно или служба недоступна, при вызове метода `GetObject` будет возвращена ошибка "Синтаксическая ошибка".  При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.  
  
     Хотя в этом разделе описывается использование моникера службы из кода VB 6.0, моникер службы можно использовать для любого другого языка.  При использовании моникера из кода C\+\+ сбоку, созданную с помощью средства Svcutil.exe, необходимо импортировать с атрибутом "no\_namespace named\_guids raw\_interfaces\_only", как показано в следующем примере кода.  
  
    ```  
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     При этом изменяются определения импортированного интерфейса, чтобы все методы возвращали `HResult`.  Все остальные возвращаемые значения преобразуются в выходные параметры.  Общий процесс выполнения методов остается прежним.  Это позволяет определить причину исключения при вызове метода в прокси.  Эта функция доступна только в коде C\+\+.  
  
## См. также  
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
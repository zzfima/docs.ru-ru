---
title: "Пошаговое руководство. доступ к веб-службы с помощью поставщиков типов (F #)"
description: "Сведения об использовании поставщика типов языка описания веб-служб (WSDL), доступные в F # 3.0 для доступа к службе языка WSDL."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 2929198172a4e9f908daa64af19208e07859263f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a>Пошаговое руководство. Доступ к веб-службе с помощью поставщиков типов

> [!NOTE]
В этом руководстве, была написана для F # 3.0 и будут обновлены.  Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](https://fsharp.github.io/FSharp.Data/).

> [!NOTE]
Справочные ссылки API, вы перейдете MSDN.  Работа над справочником по API docs.microsoft.com не завершена.

В этом пошаговом руководстве демонстрируется использование поставщика типов языка описания веб-служб (WSDL), который доступен в F # 3.0 для доступа к службе языка WSDL. В других языках .NET при создании кода для доступа к веб-службы путем вызова svcutil.exe или путем добавления веб-ссылки в, например, C# проекта для получения Visual Studio для вызова svcutil.exe. В языке F # имеется дополнительная возможность с помощью поставщика типов WSDL, так как только вы написать код, который создает типов WsdlService, типы создаются и становятся доступными. Этот процесс зависит от службы, будут доступны при написании кода.

В данном пошаговом руководстве рассмотрены следующие задачи. Необходимо выполнить их в указанном порядке для данного пошагового руководства для успешного выполнения.


- Создание проекта
<br />

- Настройка поставщика типов
<br />

- Вызов веб-службы и обработки результатов
<br />


## <a name="creating-the-project"></a>Создание проекта
На шаге создайте проект и добавляются необходимые ссылки на использование поставщика типов WSDL.


#### <a name="to-create-and-set-up-an-f-project"></a>Действия для создания и настройки проекта F#

1. Откройте новый проект консольного приложения F #.
<br />

2. В **обозревателе решений**, откройте контекстное меню для проекта **ссылки** узел и выберите **добавить ссылку**.
<br />

3. В **сборки** области, выберите **Framework**, а затем в списке доступных сборок выберите **System.Runtime.Serialization** и  **System.ServiceModel**.
<br />

4. В **сборки** области, выберите **расширения**.
<br />

5. В списке доступных сборок выберите **FSharp.Data.TypeProviders**, а затем выберите **ОК** кнопку, чтобы добавить ссылки на следующие сборки.
<br />

## <a name="configuring-the-type-provider"></a>Настройка поставщика типов
На этом шаге поставщик типов WSDL используется для создания типов для веб-службы TerraServer.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>Настройка поставщика типов и создание типов

1. Добавьте следующую строку кода, чтобы открыть пространство имен поставщика типа.
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. Добавьте следующую строку кода для вызова поставщик типов с веб-службы. В этом примере используется TerraServer веб-службы.
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "https://terraserver-usa.com/TerraService2.asmx?WSDL" https://msrmaps.com/TerraService2.asmx?WSDL">
```

  Красная волнистая линия появится под этой строкой кода, если URI службы с ошибкой или если сама служба не работает или не работает. Если навести указатель на код, сообщение об ошибке описание проблемы. Можно получить те же сведения, в **список ошибок** окно или в **окно вывода** после построения.
<br />  Существует два способа указать параметры конфигурации для подключения к WSDL, с помощью файла app.config проекта или с помощью параметров статический тип в объявлении типа поставщика. Можно использовать svcutil.exe для создания элементов файла соответствующей конфигурации. Дополнительные сведения об использовании svcutil.exe для создания сведений о конфигурации для веб-службы см. в разделе [ServiceModel Metadata Utility Tool &#40; Svcutil.exe &#41; ](https://msdn.microsoft.com/library/aa347733.aspx). Полное описание параметров статический тип поставщика типов WSDL см. в разделе [поставщика типов WsdlService](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a>Вызов веб-службы и обработки результатов
Каждая веб-служба имеет свой собственный набор типов, которые используются в качестве параметров для вызова его методов. На этом этапе подготовки этих параметров, вызов метода веб- и обработки информации, которую он возвращает.


#### <a name="to-call-the-web-service-and-process-the-results"></a>Для вызова веб-службы и обработки результатов

1. Веб-служба может время ожидания или остановке, поэтому вызов веб-службы следует включить в блок обработчика исключений. Напишите следующий код для получения данных из веб-службы.
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

Обратите внимание, создаваемые типы данных, которые необходимы для веб-службы, такие как **месте** и **расположение**, как вложенные типы под WsdlService типов **TerraService**.
<br />


## <a name="see-also"></a>См. также
[Поставщик типов WsdlService](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[Поставщики типов](index.md)

---
title: -link (параметры компилятора C#)
ms.date: 07/20/2015
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
ms.openlocfilehash: 4c96f7be5ac500886ea036c93b4651fa814ee58a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970109"
---
# <a name="-link-c-compiler-options"></a>-link (параметры компилятора C#)
Дает компилятору указание сделать всю информацию о типах COM из указанных сборок доступной компилируемому проекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-link:fileList  
// -or-  
-l:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
 `fileList`  
 Обязательный. Список всех имен файлов сборки, разделенных запятыми. Если имя файла содержит пробел, заключите его в кавычки.  
  
## <a name="remarks"></a>Remarks  
 Параметр `-link` позволяет развернуть приложение, содержащее внедренные сведения о типе. После этого приложение может использовать типы из сборки среды выполнения, реализующей информацию о внедренных типах, без ссылки на эту сборку. Если опубликовано несколько версий сборки среды выполнения, приложение, содержащее сведения о внедренных типах, может работать с различными версиями без перекомпиляции. Пример см. в разделе [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](../../../standard/assembly/embed-types-visual-studio.md).  
  
 Параметр `-link` особенно полезен при работе с COM-взаимодействием. COM-типы внедряются для того, чтобы приложению не требовалась основная сборка взаимодействия (PIA) на целевом компьютере. Параметр `-link` предписывает компилятору внедрить сведения о COM-типах из указанной сборки взаимодействия в полученный скомпилированный код. COM-тип определяется значением CLSID (GUID). Это позволяет запускать приложение на целевом компьютере, где установлены те же COM-типы с такими же значениями CLSID. В качестве примера можно привести приложения, автоматизирующие Microsoft Office. Поскольку в приложениях типа Office значение CLSID обычно не зависит от версии, ваше приложение сможет использовать COM-типы по ссылке до тех пора, пока на целевом компьютере установлена платформа .NET Framework 4 или более поздней версии, а приложение работает с методами, свойствами или событиями, включенными в эти COM-типы.  
  
 Параметр `-link` внедряет только интерфейсы, структуры и делегаты. Внедрение COM-классов не поддерживается.  
  
> [!NOTE]
> Если в коде создается экземпляр внедренного COM-типа, его следует создавать, используя соответствующий интерфейс. При попытке создать экземпляр внедренного COM-типа с помощью компонентного класса возникнет ошибка.  
  
 Чтобы задать параметр `-link` в Visual Studio, добавьте ссылку на сборку и задайте для свойства `Embed Interop Types` значение **true**. По умолчанию для свойства `Embed Interop Types` задается значение **false**.  
  
 Ссылаясь на COM-сборку (сборку A), которая, в свою очередь, ссылается на другую COM-сборку (сборку Б), необходимо также добавить ссылку на сборку Б, если выполняется любое из следующих условий:  
  
- Тип из сборки A наследуется из типа или реализует интерфейс сборки Б.  
  
- Вызывается поле, свойство, событие или метод, имеющий тип возвращаемого значения или тип параметра из сборки Б.  
  
 Как и параметр компилятора [-reference](./reference-compiler-option.md), параметр компилятора `-link` использует файл ответов Csc.rsp, который ссылается на часто используемые сборки .NET Framework. Если вы не хотите, чтобы компилятор использовал файл Csc.rsp, примените параметр компилятора [-noconfig](./noconfig-compiler-option.md).  
  
 Краткой формой `-link` является `-l`.  
  
## <a name="generics-and-embedded-types"></a>Универсальные и внедренные типы  
 В следующих разделах описаны ограничения на использование универсальных типов в приложениях с внедренными типами взаимодействия.  
  
### <a name="generic-interfaces"></a>Универсальные интерфейсы  
 Использовать универсальные интерфейсы, внедренные из сборки взаимодействия, нельзя. Это показано в следующем примере.  
  
 [!code-csharp[VbLinkCompilerCS#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#1)]  
  
### <a name="types-that-have-generic-parameters"></a>Типы с универсальными параметрами  
 Типы с универсальным параметром, тип которого внедрен из сборки взаимодействия, нельзя использовать, если он относится к внешней сборке. Это ограничение не относится к интерфейсам. Например, рассмотрим интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, который определен в сборке <xref:Microsoft.Office.Interop.Excel>. Если библиотека содержит внедренные типы взаимодействия из сборки <xref:Microsoft.Office.Interop.Excel> и предоставляет метод, возвращающий универсальный тип с параметром, типом которого является интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, этот метод должен возвращать универсальный интерфейс, как показано в следующем примере кода.  
  
 [!code-csharp[VbLinkCompilerCS#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs#2)]  
[!code-csharp[VbLinkCompilerCS#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs#3)]  
[!code-csharp[VbLinkCompilerCS#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs#4)]  
  
 В следующем примере клиентский код может вызывать метод, возвращающий универсальный интерфейс <xref:System.Collections.IList> без ошибок.  
  
 [!code-csharp[VbLinkCompilerCS#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#5)]  
  
## <a name="example"></a>Пример  
 Следующий код компилирует исходный файл `OfficeApp.cs` и ссылочные сборки из `COMData1.dll` и `COMData2.dll` и создает, таким образом, файл `OfficeApp.exe`.  
  
```csharp  
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs  
```  
  
## <a name="see-also"></a>См. также раздел

- [Параметры компилятора C# ](./index.md)
- [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](../../../standard/assembly/embed-types-visual-studio.md)
- [-reference (параметры компилятора C#)](./reference-compiler-option.md)
- [-noconfig (параметры компилятора C#)](./noconfig-compiler-option.md)
- [Сборка из командной строки с помощью csc.exe](./command-line-building-with-csc-exe.md)
- [Общие сведения о взаимодействии](../../programming-guide/interop/interoperability-overview.md)

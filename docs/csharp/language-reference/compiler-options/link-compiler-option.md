---
title: "-link (параметры компилятора C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
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
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3096dd622a0b7c5fae13412a95322b934bd38b76
ms.lasthandoff: 03/13/2017

---
# <a name="link-c-compiler-options"></a>/link (параметры компилятора C#)
Дает компилятору указание сделать всю информацию о типах COM из указанных сборок доступной компилируемому проекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/link:fileList  
// -or-  
/l:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
 `fileList`  
 Обязательный. Список всех имен файлов сборки, разделенных запятыми. Если имя файла содержит пробел, заключите его в кавычки.  
  
## <a name="remarks"></a>Примечания  
 Параметр `/link` позволяет развернуть приложение, содержащее внедренные сведения о типе. После этого приложение может использовать типы из сборки среды выполнения, реализующей информацию о внедренных типах, без ссылки на эту сборку. Если опубликовано несколько версий сборки среды выполнения, приложение, содержащее сведения о внедренных типах, может работать с различными версиями без перекомпиляции. Пример см. в разделе [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).  
  
 Параметр `/link` особенно полезен при работе с COM-взаимодействием. COM-типы внедряются для того, чтобы приложению не требовалась основная сборка взаимодействия (PIA) на целевом компьютере. Параметр `/link` предписывает компилятору внедрить сведения о COM-типах из указанной сборки взаимодействия в полученный скомпилированный код. COM-тип определяется значением CLSID (GUID). Это позволяет запускать приложение на целевом компьютере, где установлены те же COM-типы с такими же значениями CLSID. В качестве примера можно привести приложения, автоматизирующие Microsoft Office. Поскольку в приложениях типа Office значение CLSID обычно не зависит от версии, ваше приложение сможет использовать COM-типы по ссылке до тех пора, пока на целевом компьютере установлена платформа .NET Framework 4 или более поздней версии, а приложение работает с методами, свойствами или событиями, включенными в эти COM-типы.  
  
 Параметр `/link` внедряет только интерфейсы, структуры и делегаты. Внедрение COM-классов не поддерживается.  
  
> [!NOTE]
>  Если в коде создается экземпляр внедренного COM-типа, его следует создавать, используя соответствующий интерфейс. При попытке создать экземпляр внедренного COM-типа с помощью компонентного класса возникнет ошибка.  
  
 Чтобы задать параметр `/link` в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], добавьте ссылку на сборку и задайте для свойства `Embed Interop Types` значение **true**. По умолчанию для свойства `Embed Interop Types` задается значение **false**.  
  
 Ссылаясь на COM-сборку (сборку A), которая, в свою очередь, ссылается на другую COM-сборку (сборку Б), необходимо также добавить ссылку на сборку Б, если выполняется любое из следующих условий:  
  
-   Тип из сборки A наследуется из типа или реализует интерфейс сборки Б.  
  
-   Вызывается поле, свойство, событие или метод, имеющий тип возвращаемого значения или тип параметра из сборки Б.  
  
 Как и параметр компилятора [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md), параметр компилятора `/link` использует файл ответов Csc.rsp, который ссылается на часто используемые сборки [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Если вы не хотите, чтобы компилятор использовал файл Csc.rsp, примените параметр компилятора [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md).  
  
 Краткой формой `/link` является `/l`.  
  
## <a name="generics-and-embedded-types"></a>Универсальные и внедренные типы  
 В следующих разделах описаны ограничения на использование универсальных типов в приложениях с внедренными типами взаимодействия.  
  
### <a name="generic-interfaces"></a>Универсальные интерфейсы  
 Использовать универсальные интерфейсы, внедренные из сборки взаимодействия, нельзя. Эти действия показаны в следующем примере.  
  
 [!code-cs[VbLinkCompilerCS#1](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_1.cs)]  
  
### <a name="types-that-have-generic-parameters"></a>Типы с универсальными параметрами  
 Типы с универсальным параметром, тип которого внедрен из сборки взаимодействия, нельзя использовать, если он относится к внешней сборке. Это ограничение не относится к интерфейсам. Рассмотрим, например, интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, определяемый в сборке <xref:Microsoft.Office.Interop.Excel>. Если библиотека содержит внедренные типы взаимодействия из сборки <xref:Microsoft.Office.Interop.Excel> и предоставляет метод, возвращающий универсальный тип с параметром, типом которого является интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, этот метод должен возвращать универсальный интерфейс, как показано в следующем примере кода.  
  
 [!code-cs[VbLinkCompilerCS#2](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_2.cs)]  
[!code-cs[VbLinkCompilerCS#3](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_3.cs)]  
[!code-cs[VbLinkCompilerCS#4](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_4.cs)]  
  
 В следующем примере клиентский код может вызывать метод, возвращающий универсальный интерфейс <xref:System.Collections.IList> без ошибок.  
  
 [!code-cs[VbLinkCompilerCS#5](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_5.cs)]  
  
## <a name="example"></a>Пример  
 Следующий код компилирует исходный файл `OfficeApp.cs` и ссылочные сборки из `COMData1.dll` и `COMData2.dll` и создает, таким образом, файл `OfficeApp.exe`.  
  
```csharp  
csc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)   
 [/reference (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)   
 [/noconfig (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)   
 [Сборка из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Общие сведения о взаимодействии](../../../csharp/programming-guide/interop/interoperability-overview.md)

---
title: "-appconfig (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /appconfig
dev_langs:
- CSharp
helpviewer_keywords:
- /appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
caps.latest.revision: 26
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2aede966f92af3c94f4591b68732dbdbf5a4c5c9
ms.contentlocale: ru-ru
ms.lasthandoff: 09/19/2017

---
# <a name="appconfig-c-compiler-options"></a>/appconfig (параметры компилятора C#)
Параметр компилятора **/appconfig** позволяет приложению C# задать расположение файла конфигурации приложения сборки (app.config) в среде CLR во время привязки сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/appconfig:file  
```  
  
## <a name="arguments"></a>Аргументы  
 `file`  
 Обязательный. Файл конфигурации приложения, содержащий параметры привязки сборки.  
  
## <a name="remarks"></a>Примечания  
 Один из случаев использования параметра **/appconfig** — сложные сценарии, когда в сборке одновременно используются ссылки и на версию .NET Framework, и на версию .NET Framework для Silverlight определенной ссылочной сборки. Например, для конструктора XAML, написанного в Windows Presentation Foundation (WPF), может потребоваться ссылаться на оба рабочих стола WPF, для пользовательского интерфейса конструктора и для подмножества WPF, поставляемого с Silverlight. Одна и та же сборка конструктора имеет доступ к обеим сборкам. По умолчанию отдельные ссылки вызывают ошибку компиляции, так как привязка сборки видит две эквивалентные сборки.  
  
 Параметр компилятора **/appconfig** позволяет указать расположение файла app.config, который отключает поведение по умолчанию с помощью тега `<supportPortability>`, как показано в следующем примере.  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 Компилятор передает расположение файла в логику с привязкой сборки среды CLR.  
  
> [!NOTE]
>  При построении приложения с помощью Microsoft Build Engine (MSBuild) можно задать параметр компилятора **/appconfig**, добавив тег свойства в CSPROJ-файл. Чтобы использовать файл app.config, уже заданный в проекте, добавьте тег свойства `<UseAppConfigForCompiler>` в CSPROJ-файл и задайте для него значение `true`. Чтобы указать другой файл app.config, добавьте тег свойства `<AppConfigForCompiler>` и задайте в качестве его значения расположение требуемого файла.  
  
## <a name="example"></a>Пример  
 В следующем примере показан файл app.config, позволяющий приложению иметь ссылки на реализации .NET Framework и .NET Framework для реализации Silverlight любой сборки .NET Framework, существующей в обеих реализациях. Параметр компилятора **/appconfig** указывает расположение этого файла app.config.  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об унификации сборок платформы .NET Framework](http://msdn.microsoft.com/en-us/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)   
 [Элемент \<supportPortability>](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)   
 [Параметры компилятора C# в алфавитном порядке](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)


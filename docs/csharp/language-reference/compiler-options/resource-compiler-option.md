---
title: "-resource (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 726956275436e22723bc32b98b2b8b7c7df5fb12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="resource-c-compiler-options"></a>/resource (параметры компилятора C#)
Внедряет указанный ресурс в выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Файл ресурсов платформы .NET Framework, который требуется внедрить в выходной файл.  
  
 `identifier` (необязательно)  
 Логическое имя ресурса, используемое для его загрузки. По умолчанию используется имя файла.  
  
 `accessibility-modifier` (необязательно)  
 Доступность ресурса: "public" (открытый) или "private" (закрытый). Значение по умолчанию — "public" (открытый).  
  
## <a name="remarks"></a>Примечания  
 С помощью параметра [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) можно связать ресурс со сборкой, в результате чего не потребуется добавлять файл ресурсов в выходной файл.  
  
 По умолчанию ресурсы в сборке открыты, если они создавались с помощью компилятора C#. Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступа. Уровни доступности, отличные от `public` или `private`, не допускаются.  
  
 Если `filename` является файлом ресурсов .NET Framework, созданным, например, с помощью [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources>. Для получения дополнительной информации см. <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Другие ресурсы, используйте `GetManifestResource` методы в <xref:System.Reflection.Assembly> класса доступа к ресурсам во время выполнения.  
  
 **/res** является краткой формой **/resource**.  
  
 Порядок расположения ресурсов в выходном файле будет определяться порядком, указанным в командной строке.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Добавьте файл ресурсов в проект.  
  
2.  Выберите файл, который требуется внедрить, в **обозревателе решений**.  
  
3.  Выберите **Действие сборки** для файла в окне **Свойства**.  
  
4.  Присвойте параметру **Действие сборки** значение **Внедренный ресурс**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## <a name="example"></a>Пример  
 Компиляция `in.cs` и привязка файла ресурсов `rf.resource`:  
  
```console  
csc /resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

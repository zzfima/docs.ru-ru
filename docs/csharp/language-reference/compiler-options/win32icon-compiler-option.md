---
title: "-win32icon (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32icon
dev_langs:
- CSharp
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 18
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
ms.openlocfilehash: af5b9c3a44163167d932d378cbac4976e07eacbf
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="win32icon-c-compiler-options"></a>/win32icon (параметры компилятора C#)
Параметр **/win32icon** вставляет в выходной файл ICO-файл, который придает выходному файлу необходимый вид в проводнике.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/win32icon:filename  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 ICO-файл, который требуется добавить в выходной файл.  
  
## <a name="remarks"></a>Примечания  
 ICO-файл можно создать с помощью [компилятора ресурсов](http://go.microsoft.com/fwlink/?LinkId=148370). Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла.  
  
 Дополнительные сведения о ссылках на файлы ресурсов .NET Framework и их присоединении см. в разделах [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) и [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) соответственно. Дополнительные сведения об импорте RES-файла см. в разделе [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Перейдите на страницу свойств **Приложение**.  
  
3.  Измените свойство **Значок приложения**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.  
  
## <a name="example"></a>Пример  
 Скомпилируйте `in.cs` и присоедините ICO-файл `rf.ico`, чтобы получить файл `in.exe`:  
  
```console  
csc /win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)


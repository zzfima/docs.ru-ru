---
title: "-nostdlib (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nostdlib
dev_langs:
- CSharp
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1d500e2e55ab3117aa674e11d6cdd25703035879
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="nostdlib-c-compiler-options"></a>/nostdlib (параметры компилятора C#)
Параметр**/nostdlib** запрещает импорт библиотеки mscorlib.dll, которая определяет все пространство имен System.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/nostdlib[+ | -]  
```  
  
## <a name="remarks"></a>Примечания  
 Используйте этот параметр, если вы хотите определить или создать собственное пространство имен System и объекты.  
  
 Если вы не укажете параметр **/nostdlib**, библиотека mscorlib.dll будет импортирована в вашу программу (как и при указании **/nostdlib-**). Указание **/nostdlib** дает тот же результат, что и указание **/nostdlib+**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **свойств** для проекта.  
  
2.  Щелкните страницу свойств **сборки** .  
  
3.  Нажмите кнопку **Дополнительно** .  
  
4.  Измените свойство **Не ссылаться на mscorlib.dll** .  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)


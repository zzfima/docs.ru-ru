---
title: "-nostdlib (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad3ca7775512623de43c7fe6b7fe1cf481ccca87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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

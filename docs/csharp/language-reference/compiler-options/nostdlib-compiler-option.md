---
title: -nostdlib (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 1dc0ab70ca28626c4a3f505c13ec1d6f828a4b05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216139"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (параметры компилятора C#)
Параметр **-nostdlib** запрещает импорт библиотеки mscorlib.dll, которая определяет все пространство имен System.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-nostdlib[+ | -]  
```  
  
## <a name="remarks"></a>Примечания  
 Используйте этот параметр, если вы хотите определить или создать собственное пространство имен System и объекты.  
  
 Если вы не укажете параметр **-nostdlib**, библиотека mscorlib.dll будет импортирована в вашу программу (как и при указании **-nostdlib-**). Указание **-nostdlib** дает тот же результат, что и указание **-nostdlib+**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **свойств** для проекта.  
  
2.  Щелкните страницу свойств **сборки** .  
  
3.  Нажмите кнопку **Дополнительно** .  
  
4.  Измените свойство **Не ссылаться на mscorlib.dll** .  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)

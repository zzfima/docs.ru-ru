---
title: -warnaserror (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: a29b0a6095453e3d2747cad9d9f71b463d8f6b1f
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081505"
---
# <a name="-warnaserror-c-compiler-options"></a>-warnaserror (параметры компилятора C#)
Параметр **-warnaserror+** предписывает обрабатывать все предупреждения как ошибки  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a>Примечания  
 Все сообщения, которые до этого получали статус предупреждений, будут возвращаться как ошибки, в результате чего процесс построения прерывается без создания выходных файлов.  
  
 По умолчанию действует параметр **-warnaserror-**, при котором наличие предупреждений не препятствует созданию выходного файла. Если задан параметр **-warnaserror** или эквивалентный ему **-warnaserror+**, все предупреждения обрабатываются как ошибки.  
  
 Если требуется обрабатывать как ошибки только конкретные предупреждения, укажите их номера через запятую.  
  
 Параметр [-warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) позволяет указать уровень предупреждений, которые будет отображать компилятор. Параметр [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) позволяет отключать определенные предупреждения.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Щелкните страницу свойств **Сборка**.  
  
3.  Измените свойство **Обрабатывать предупреждения как ошибки**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.  
  
## <a name="example"></a>Пример  
 Компиляция файла `in.cs` без отображения предупреждений:  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a>См. также  

- [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

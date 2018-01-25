---
title: "-warn (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6a1f2c55aa078adb213a93dc5aff7ced40793bfa
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-warn-c-compiler-options"></a>-warn (параметры компилятора C#)
Параметр **-warn** задает уровень предупреждений, которые должны отображаться компилятором.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a>Аргументы  
 `option`  
 При меньших значениях уровня предупреждений отображаются только самые серьезные предупреждения. Чем выше значение, тем больше предупреждений будет отображаться. Допускаются значения от 0 до 4:  
  
|Уровень предупреждений|Значение|  
|-------------------|-------------|  
|0|Отключает вывод всех предупреждающих сообщений.|  
|1|Отображает серьезные предупреждающие сообщения.|  
|2|Отображает предупреждения уровня 1, а также некоторые менее серьезные предупреждения, в том числе связанные со скрытием членов класса.|  
|3|Отображает предупреждения уровня 2, а также некоторые менее серьезные предупреждения, в том числе связанные с выражениями, которые всегда возвращают значение `true` или `false`.|  
|4 (по умолчанию)|Отображает все предупреждения уровня 3, а также информационные предупреждения.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы получить сведения об ошибке или предупреждении, выполните поиск по соответствующему коду в указателе справочной системы. Дополнительные сведения о других способах получить информацию об ошибках и предупреждениях см. в разделе [Ошибки компилятора C#](../../../csharp/language-reference/compiler-messages/index.md).  
  
 Параметр [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) позволяет обрабатывать все предупреждения как ошибки. Параметр [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) позволяет отключать определенные предупреждения.  
  
 **-w** является краткой формой **-warn**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Щелкните страницу свойств **Сборка**.  
  
3.  Измените свойство **Порог предупреждений**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.  
  
## <a name="example"></a>Пример  
 Компиляция файла `in.cs` с отображением только предупреждений уровня 1:  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

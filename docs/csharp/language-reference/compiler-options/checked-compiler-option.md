---
title: "-checked (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: 20
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
ms.openlocfilehash: 63ba89ec42748ccea065bf0fd258fb559abca099
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-compiler-options"></a>/checked (параметры компилятора C#)
Параметр **/checked** указывает, будет ли находящийся вне области действия ключевых слов [checked](../../../csharp/language-reference/keywords/checked.md) или [unchecked](../../../csharp/language-reference/keywords/unchecked.md) целочисленный арифметический оператор, в результате выполнения которого получено значение, выходящее за установленный для данного типа данных диапазон значений, приводить к возникновению исключения во время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/checked[+ | -]  
```  
  
## <a name="remarks"></a>Примечания  
 Действие параметра **/checked** не затрагивает целочисленный арифметический оператор, находящийся вне области действия ключевых слов `checked` или `unchecked`.  
  
 Если в результате выполнения целочисленного арифметического оператора, находящегося вне области действия ключевых слов `checked` или `unchecked`, получено значение, выходящее за установленный для данного типа данных диапазон значений, и в компиляции использовался **/checked+** (**/checked**), то этот оператор будет приводить к возникновению исключения во время выполнения. Если в компиляции использовался **/checked-**, оператор не будет приводить к исключению во время выполнения.  
  
 **/checked-** является значением по умолчанию для данного параметра. Одним из сценариев использования **/checked-** является создание крупных приложений. Иногда автоматизированные средства используются для построения подобных приложений, и в данной ситуации они могут автоматически задать + для **/checked**. Чтобы переопределить глобальное значение по умолчанию, задайте**/checked-**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта. Дополнительные сведения см. в разделе [Страница "Сборка" в конструкторе проектов (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2.  Щелкните страницу свойств **Сборка**.  
  
3.  Нажмите кнопку **Дополнительно** .  
  
4.  Измените свойство **Проверять арифметические переполнения и потери точности**.  
  
 Программный доступ к этому параметру компилятора описан в статье <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда используется для компиляции `t2.cs`. Использование `/checked` в команде указывает, что целочисленный арифметический оператор, находящийся вне области действия ключевых слов `checked` или `unchecked`, и значение результата его выполнения, выходящее за установленный для данного типа данных диапазон значений, будут приводить к возникновению исключения во время выполнения.  
  
```console  
csc t2.cs /checked  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)   
 [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)


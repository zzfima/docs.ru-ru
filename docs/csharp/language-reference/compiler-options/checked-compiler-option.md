---
title: "/checked (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/checked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked compiler option [C#]"
  - "-checked compiler option [C#]"
  - "/checked compiler option [C#]"
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /checked (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр **\/checked** указывает, будет ли целочисленный арифметический оператор, в результате выполнения которого получено значение, выходящее за установленный для данного типа данных диапазон значений и который находится вне области действия ключевого слова [checked](../../../csharp/language-reference/keywords/checked.md) или [unchecked](../../../csharp/language-reference/keywords/unchecked.md), приводить к возникновению исключения во время выполнения.  
  
## Синтаксис  
  
```  
/checked[+ | -]  
```  
  
## Заметки  
 Действие параметра **\/checked** не затрагивает целочисленный арифметический оператор, находящийся в области действия ключевого слова `checked` или `unchecked`.  
  
 Если в результате выполнения целочисленного арифметического оператора, находящегося вне области действия ключевого слова `checked` или `unchecked`, получено значение, выходящее за установленный для данного типа данных диапазон значений, и в компиляции использовался **\/checked\+** \(**\/checked**\), то этот оператор приводит к возникновению исключения во время выполнения.  Если в компиляции использовался **\/checked\-**, оператор не приводит к исключению во время выполнения.  
  
 Значение этого свойства по умолчанию равно **\/checked\-**.  Один сценарий для использования **\/checked\-** — создание больших приложений.  Иногда автоматизированные инструменты используются для построения таких приложений, и такой инструмент может автоматически устанавливать для **\/checked** значение \+.  Можно переопределить глобальные настройки инструмента по умолчанию, задав параметр **\/checked\-**.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  Для получения дополнительной информации см. [Страница "Построение" в конструкторе проектов \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp).  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Нажмите кнопку **Дополнительно**.  
  
4.  Измените свойство **Проверять арифметические переполнения и потери точности**.  
  
 Сведения о программном доступе к этому параметру компилятора см. в <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.  
  
## Пример  
 Следующая команда компилирует `t2.cs`.  Использование параметра `/checked` в команде указывает, что любое целочисленное арифметическое выражение в файле, не входящее в область ключевого слова `checked` или `unchecked` и дающее значение, выходящее за пределы диапазона типа данных, вызывает исключение во время выполнения.  
  
```  
csc t2.cs /checked  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7)
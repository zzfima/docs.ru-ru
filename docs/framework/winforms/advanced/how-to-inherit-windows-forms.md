---
title: "Практическое руководство. Наследование форм Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "наследование, формы"
  - "наследуемые формы, создание во время выполнения"
  - "Windows Forms, наследование"
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Наследование форм Windows Forms
Создание новых форм Windows Forms путем наследования базовых форм является удобным способом для дублирования уже созданного, минуя процесс повторного создания формы с нуля каждый раз, когда она необходима.  
  
 Дополнительные сведения о наследовании форм во время разработки с помощью диалогового окна **Выбор компонентов для наследования** и как визуально различать уровни безопасности производных элементов управления см. в разделе [Практическое руководство. Наследование форм с помощью диалогового окна выбора наследования](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).  
  
 **Примечание** Чтобы произвести наследование от формы, файл или пространство имен, содержащие форму, должны быть встроены в исполняемый файл или библиотеку DLL.  Для сборки проекта выберите в меню **Сборка** пункт **Собрать**.  Кроме того необходимо добавить ссылку на пространство имен к классу, наследующему форму.  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.  Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Наследование формы программными средствами  
  
1.  В классе добавьте ссылку на пространство имен, содержащее форму, которую вы хотите наследовать.  
  
2.  В определении класса добавьте ссылку на форму для наследования.  Ссылка должна содержать пространство имен, в котором содержится форма, точку, а затем имя базовой формы.  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
  
    ```  
  
 При наследовании форм следует помнить, что могут возникнуть проблемы с обработчиками событий, которые вызываются дважды, так как каждое событие обрабатывается базовым классом и производным классом.  Дополнительные сведения о том, как избежать этой проблемы см. в разделе [Устранение неполадок, связанных с унаследованными обработчиками событий в Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md).  
  
## См. также  
 [Инструкция Inherits](../../../../ocs/visual-basic/language-reference/statements/inherits-statement.md)   
 [Оператор Imports \(пространство имен .NET и тип\)](../../../../ocs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [использование](../Topic/using%20\(C%23%20Reference\).md)   
 [Влияние изменения внешнего вида базовой формы](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)   
 [Визуальное наследование в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
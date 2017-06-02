---
title: "Практическое руководство. Формирование макета формы Windows Forms с учетом будущей локализации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "разработка приложений, локализация"
  - "локализация, макет Windows Forms"
  - "TableLayoutPanel - элемент управления [Windows Forms]"
  - "Windows Forms, локализация"
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Формирование макета формы Windows Forms с учетом будущей локализации
Создание готовых для локализации форм значительно ускоряет разработку продуктов для международных рынков.  Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> можно использовать для реализации макетов, которые поддерживают изменение размера элементов управления при изменении значений их свойств <xref:System.Windows.Forms.Control.Text%2A>.  
  
## Пример  
 Эта форма показывает, как создать макет, который пропорционально корректируется при отображении строковых значений на других языках.  Такой процесс перевода называется *локализацией*.  Подробнее об этом см. в разделе [Локализация](../../../../docs/standard/globalization-localization/localization.md).  
  
 В Visual Studio предусмотрена расширенная поддержка этой задачи.  См. также [Пошаговое руководство. Создание структуры, сохраняющей пропорции при локализации](http://msdn.microsoft.com/ru-ru/library/7k9fa71y\(v=vs.110\))  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))  
  
2.  [Пример. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).  
  
3.  [Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))  
  
4.  [Практическое руководство. Редактирование строк и столбцов в элементе управления TableLayoutPanel](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))  
  
5.  [Пример. Выполнение типичных задач с помощью смарт\-тегов в элементах управления Windows Forms](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))  
  
6.  [Пример. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\)).  
  
7.  [Пример. Создание структуры элементов управления Windows Forms с помощью свойств "Заполнение", "Поля" и "Авторазмер"](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).  
  
8.  [Практическое руководство. Обеспечение поддержки локализации в Windows Forms с помощью элементов управления AutoSize и TableLayoutPanel](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))  
  
9. [Пример. Создание в Windows Forms формы для ввода данных переменного размера](http://msdn.microsoft.com/library/991eahec\(v=vs.110\)).  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Вы можете выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 [Локализация](../../../../docs/standard/globalization-localization/localization.md)
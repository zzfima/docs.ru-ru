---
title: "Создание и использование компонентов в Visual Basic | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "компоненты [Visual Basic]"
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Создание и использование компонентов в Visual Basic
[!INCLUDE[vs2017banner](../../visual-basic/includes/vs2017banner.md)]

*Компонент* представляет собой класс, реализующий интерфейс <xref:System.ComponentModel.IComponent?displayProperty=fullName>, или производный прямо или косвенно от класса, реализующего интерфейс <xref:System.ComponentModel.IComponent>.  Компонент [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)] — это многократно используемый объект, который может взаимодействовать с другими объектами и обеспечивает управление внешними ресурсами и поддержку режима проектирования.  
  
 Важной особенностью компонентов является то, что они поддерживают проектирование, что означает, что класс\-компонент может быть использован в интегрированной среде разработки [!INCLUDE[vsprvs](../../csharp/includes/vsprvs-md.md)].  Компонент можно добавить в "Панель элементов", перетащить на форму и манипулировать им на поверхности проектирования.  Отметим, что базовая поддержка режима проектирования для компонентов встроена в [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)]; разработчику компонентов не нужно прикладывать дополнительные усилия, чтобы воспользоваться ее преимуществами при проектировании.  
  
 *Элемент управления* похож на компонент, так как он тоже поддерживает проектирование.  Но в отличие от компонента, элемент управления предоставляет пользовательский интерфейс.  Элемент управления должен быть прямо или косвенно производным от одного из следующих базовых классов элементов управления: <xref:System.Windows.Forms.Control> или <xref:System.Web.UI.Control>.  
  
## Когда следует создавать компонент  
 Если класс будет использоваться на поверхности проектирования \(например Windows Forms или конструктора Web Forms\), но у него нет пользовательского интерфейса, он должен быть компонентом и реализовывать <xref:System.ComponentModel.IComponent> либо быть производным от класса, который прямо или косвенно реализующего интерфейс <xref:System.ComponentModel.IComponent>.  
  
 Классы <xref:System.ComponentModel.Component> и <xref:System.ComponentModel.MarshalByValueComponent> являются базовой реализацией интерфейса <xref:System.ComponentModel.IComponent>.  Главное различие между этими классами состоит в том, что маршалинг класса <xref:System.ComponentModel.Component> производится по ссылке, а класса <xref:System.ComponentModel.IComponent> — по значению.  Следующий список содержит общие принципы реализации.  
  
-   Если компонент нужно будет маршалировать по ссылке, он должен быть производным от класса <xref:System.ComponentModel.Component>.  
  
-   Если компонент нужно будет маршалировать по значению, он должен быть производным от класса <xref:System.ComponentModel.MarshalByValueComponent>.  
  
-   Если компонент не может быть производным от одной из базовых реализации из\-за единичного наследования, реализуйте интерфейс <xref:System.ComponentModel.IComponent>.  
  
 Дополнительные сведения о поддержке режима проектирования см. в разделах [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md) и [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md).  
  
## Классы компонентов  
 Пространство имен <xref:System.ComponentModel> содержит классы, реализующие поведение компонентов и элементов управления во время проектирования и выполнения.  Данное пространство имен включает базовые классы и интерфейсы, предназначенные для реализации преобразователей атрибутов и типов, для привязки к источникам данных и для лицензирования компонентов.  
  
 Основные классы компонентов:  
  
-   <xref:System.ComponentModel.Component>.  Базовая реализация интерфейса <xref:System.ComponentModel.IComponent>.  Этот класс обеспечивает совместное использование объектов приложениями.  
  
-   <xref:System.ComponentModel.MarshalByValueComponent>.  Базовая реализация интерфейса <xref:System.ComponentModel.IComponent>.  
  
-   <xref:System.ComponentModel.Container>.  Базовая реализация интерфейса <xref:System.ComponentModel.IContainer>.  Этот класс инкапсулирует ноль или более компонентов.  
  
 Некоторые классы, используемые для лицензирования компонентов:  
  
-   <xref:System.ComponentModel.License>.  Абстрактный базовый класс для всех лицензий.  Лицензия предоставляется на конкретный экземпляр компонента.  
  
-   <xref:System.ComponentModel.LicenseManager>.  Предоставляет свойства и методы, необходимые для добавления лицензии на компонент и для управления объектом <xref:System.ComponentModel.LicenseProvider>.  
  
-   <xref:System.ComponentModel.LicenseProvider>.  Абстрактный базовый класс для реализации поставщика лицензий.  
  
-   <xref:System.ComponentModel.LicenseProviderAttribute>.  Задает класс <xref:System.ComponentModel.LicenseProvider>, используемый с тем или иным классом.  
  
 Классы, обычно используемые для описания и постоянного хранения компонентов.  
  
-   <xref:System.ComponentModel.TypeDescriptor>.  Содержит сведения о характеристиках компонента, например его атрибутах, свойствах и событиях.  
  
-   <xref:System.ComponentModel.EventDescriptor>.  Предоставляет сведения о событии.  
  
-   <xref:System.ComponentModel.PropertyDescriptor>.  Предоставляет сведения о свойстве.  
  
## Связанные разделы  
 [Class vs. Component vs. Control](../Topic/Class%20vs.%20Component%20vs.%20Control.md)  
 В этом разделе определяются термины *компонент* и *элемент управления* и рассматриваются различия между ними и классами.  
  
 [Component Authoring](../Topic/Component%20Authoring.md)  
 Путеводитель для начала работы с компонентами.  
  
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)  
 Ссылки на разделы, содержащие пошаговые инструкции по программированию компонентов.  
  
 [Component Classes](../Topic/Component%20Classes.md)  
 Описание того, что делает класс компонентом, способов предоставления функциональных возможностей компонента другим приложениям, управления доступом к компонентам и созданием их экземпляров.  
  
 [Разрешение вопросов, связанных с созданием элементов управления и компонентов](../Topic/Troubleshooting%20Control%20and%20Component%20Authoring.md)  
 Способы решения распространенных проблем.  
  
## См. также  
 [How to: Access Design\-Time Support in Windows Forms](../Topic/How%20to:%20Access%20Design-Time%20Support%20in%20Windows%20Forms.md)   
 [How to: Extend the Appearance and Behavior of Controls in Design Mode](../Topic/How%20to:%20Extend%20the%20Appearance%20and%20Behavior%20of%20Controls%20in%20Design%20Mode.md)   
 [How to: Perform Custom Initialization for Controls in Design Mode](../Topic/How%20to:%20Perform%20Custom%20Initialization%20for%20Controls%20in%20Design%20Mode.md)
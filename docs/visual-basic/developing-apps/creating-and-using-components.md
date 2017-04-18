---
title: "Создание и использование компонентов в Visual Basic | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9ca4df41897fafc5d7981c85741ae4fa1a8c641f
ms.lasthandoff: 03/13/2017

---
# <a name="creating-and-using-components-in-visual-basic"></a>Создание и использование компонентов в Visual Basic
*Компонент* — это класс, реализующий интерфейс <xref:System.ComponentModel.IComponent?displayProperty=fullName> или непосредственно либо косвенно наследуемый из класса, который реализует <xref:System.ComponentModel.IComponent>. Компонент [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] является объектом, допускающим повторное использование, который может взаимодействовать с другими объектами и обеспечивает контроль над внешними ресурсами и поддержку во время разработки.  
  
 Важной особенностью компонентов является то, что они поддерживают проектирование, то есть класс, являющийся компонентом, может использоваться в интегрированной среде разработки [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)]. Компонент можно добавить на панель элементов, перетащить в форму, кроме того, с ним можно выполнять различные действия в области конструктора. Обратите внимание, что базовая поддержка во время разработки для компонентов встроена в [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)], а значит разработчику компонентов не нужно прикладывать дополнительные усилия, чтобы воспользоваться преимуществами базовых функций во время разработки.  
  
 *Элемент управления* похож на компонент, в том смысле, что оба поддерживают проектирование. Тем не менее элемент управления предоставляет пользовательский интерфейс, а компонент — нет. Элемент управления должен быть производным от одного из базовых классов элементов управления: <xref:System.Windows.Forms.Control> или <xref:System.Web.UI.Control>.  
  
## <a name="when-to-create-a-component"></a>Когда требуется создание компонента  
 Если ваш класс будет использоваться в области конструктора (например, конструктора Windows Forms или веб-форм), но у него отсутствует интерфейс пользователя, он должен быть компонентом и реализовывать интерфейс <xref:System.ComponentModel.IComponent> или быть производным от класса, который непосредственно или косвенно реализует <xref:System.ComponentModel.IComponent>.  
  
 Классы <xref:System.ComponentModel.Component> и <xref:System.ComponentModel.MarshalByValueComponent> являются базовой реализацией интерфейса <xref:System.ComponentModel.IComponent>. Основное различие между этими классами заключается в том, что для класса <xref:System.ComponentModel.Component> маршалинг выполняется по ссылке, а для класса <xref:System.ComponentModel.IComponent> — по значению. Ниже приведены общие указания по реализации.  
  
-   Если для компонента необходимо выполнить маршалинг по ссылке, он должен быть производным от <xref:System.ComponentModel.Component>.  
  
-   Если для компонента необходимо выполнить маршалинг по значению, он должен быть производным от <xref:System.ComponentModel.MarshalByValueComponent>.  
  
-   Если компонент не может быть производным от одной из базовых реализаций из-за одиночного наследования, реализуйте <xref:System.ComponentModel.IComponent>.  
  
 Дополнительные сведения о поддержке во время разработки см. в разделе [Атрибуты времени разработки для компонентов](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3) и [Расширение поддержки времени разработки](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).  
  
## <a name="component-classes"></a>Классы компонентов  
 Пространство имен <xref:System.ComponentModel> предоставляет классы, используемые для реализации поведения компонентов и элементов управления во время разработки и во время выполнения. Это пространство имен содержит базовые классы и интерфейсы для реализации атрибутов и преобразователей типов, привязки к источникам данных и лицензирования компонентов.  
  
 Ниже перечислены основные классы компонентов.  
  
-   <xref:System.ComponentModel.Component>. Базовая реализация для интерфейса <xref:System.ComponentModel.IComponent>. Этот класс обеспечивает совместное использование объектов несколькими приложениями.  
  
-   <xref:System.ComponentModel.MarshalByValueComponent>. Базовая реализация для интерфейса <xref:System.ComponentModel.IComponent>.  
  
-   <xref:System.ComponentModel.Container>. Базовая реализация для интерфейса <xref:System.ComponentModel.IContainer>. Этот класс инкапсулирует нуль или более компонентов.  
  
 Ниже приведены некоторые классы, используемые для лицензирования компонентов.  
  
-   <xref:System.ComponentModel.License>. Абстрактный базовый класс для всех лицензий. Лицензия предоставляется конкретному экземпляру компонента.  
  
-   <xref:System.ComponentModel.LicenseManager>. Предоставляет свойства и методы для добавления лицензии в компонент и для управления поставщиком <xref:System.ComponentModel.LicenseProvider>.  
  
-   <xref:System.ComponentModel.LicenseProvider>. Абстрактный базовый класс для реализации поставщика лицензий.  
  
-   <xref:System.ComponentModel.LicenseProviderAttribute>. Указывает класс <xref:System.ComponentModel.LicenseProvider> для использования с классом.  
  
 Ниже приведены классы, которые обычно используются для описания и постоянного хранения компонентов.  
  
-   <xref:System.ComponentModel.TypeDescriptor>. Предоставляет сведения о характеристиках компонента, таких как его атрибуты, свойства и события.  
  
-   <xref:System.ComponentModel.EventDescriptor>. Предоставляет сведения о событии.  
  
-   <xref:System.ComponentModel.PropertyDescriptor>. Предоставляет сведения о свойстве.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Выбор между классом компонентом и элементом управления](http://msdn.microsoft.com/library/db8b842e-44d9-40cc-a0f8-70fd189632c3)  
 Определение *компонента* и *элемента управления* и описание различий между ними и классами.  
  
 [Создание компонентов](http://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 Путеводитель по началу работы с компонентами.  
  
 [Примеры создания компонентов](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 Ссылки на разделы, содержащие пошаговые инструкции по программированию компонентов.  
  
 [Классы компонентов](http://msdn.microsoft.com/library/ce2e5647-e673-4c2b-8125-ffebbd9d71bc)  
 Сведения о том, что делает класс компонентом, а также описание способов предоставления функций компонента, управления доступом к компонентам и управления созданием экземпляров компонента.  
  
 [Разрешение вопросов, связанных с созданием элементов управления и компонентов](http://msdn.microsoft.com/library/e9c8c099-2271-4737-882f-50f336c7a55e)  
 Способы решения распространенных проблем.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Доступ к поддержке во время разработки в Windows Forms](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)   
 [Практическое руководство. Расширение внешнего вида и функциональности элементов управления в режиме конструктора](http://msdn.microsoft.com/library/68f85054-2253-47f5-a4f2-3f1ac8c9f27b)   
 [Практическое руководство. Выполнение настраиваемой инициализации для элементов управления в режиме конструктора](http://msdn.microsoft.com/library/914eaa03-092f-4556-9160-b8a2a40641d9)

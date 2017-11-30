---
title: "Директива x:Class"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 1828ef3614cc1f3a81d8aeff62c15ed5accfe380
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xclass-directive"></a>Директива x:Class
Настраивает компиляции разметки XAML для объединения разделяемых классов разметки и кода. Разделяемый класс кода определяется в отдельном файле кода в [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] языка, тогда как разделяемый класс разметки обычно создается путем создания кода во время компиляции XAML.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`namespace`|Необязательно. Указывает [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] пространство имен, содержащее разделяемый класс, определяемый `classname`. Если `namespace` указан, точка (.) отделяет `namespace` и `classname`. См. заметки.|  
|`classname`|Обязательный. Указывает [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] имя разделяемого класса, который соединяет загруженный XAML и вашего кода программной части для этого кода XAML.|  
  
## <a name="dependencies"></a>Зависимости  
 `x:Class`можно указать только в корневом элементе рабочей среды XAML. `x:Class`Недопустимый для любого объекта, есть родительский элемент в создании XAML. Дополнительные сведения см. в разделе [ \[MS-XAML\] раздел 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Примечания  
 `namespace` Значение может содержать дополнительные точки для организации связанных пространств имен в имя иерархии, который-это стандартная техника в программировании на платформе .NET Framework. Только последняя точка в строку `x:Class` интерпретации значений для разделения `namespace` и `classname.` класс, который используется в качестве `x:Class` не может быть вложенным классом. Вложенные классы не разрешены, так как при определении значения точек для `x:Class` строки является неоднозначным, если разрешены вложенные классы.  
  
 В существующей модели программирования, используйте `x:Class`, `x:Class` является необязательным в том смысле, допустимость полностью в XAML-страницы, имеющий кода не имеют. Однако эта возможность взаимодействует с действия построения, реализуемый платформы, использующие XAML. `x:Class`возможность также зависит от роли, различных классификаций определяемого XAML содержимого в модели приложения и соответствующих действий построения. Если в коде XAML объявляется значений атрибута обработки событий, или создаются пользовательские элементы, в которых определение классов в класс кода программной, вы должны предоставить `x:Class` директив ссылки (или [x: Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)) для соответствующий класс для кода.  
  
 Значение `x:Class` директива должна быть строка, указывающая полное имя класса, но не все сведения о сборке (эквивалентно <xref:System.Type.FullName%2A?displayProperty=nameWithType>). Для простых приложений можно пропустить сведения о пространстве имен среды CLR, если код программной части также структурируется таким способом (код определения начнется на уровне класса).  
  
 Файл кода для определения страницы или приложения должен быть в файле кода, который входит в состав проекта, который создается скомпилированное приложение и включает компиляцию разметки. Необходимо выполнить правила имен для классов среды CLR. Дополнительные сведения см. в разделе [рекомендации по разработке Framework](../../../docs/standard/design-guidelines/index.md). По умолчанию, должны иметь класс кода программной `public`, однако ее можно задавать на другой уровень доступа с помощью [директива x: ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
 Это интерпретацию `x:Class` атрибут применяется только к реализации XAML на основе среды CLR, в частности для служб XAML .NET Framework. Другие реализации XAML, которые не основаны на среде CLR и не использующие служб XAML .NET Framework могут использовать другую формулу разрешения для подключения разметки XAML и вспомогательного кода во время выполнения. Дополнительные сведения о дополнительной интерпретации `x:Class`, в разделе [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 На определенном уровне архитектуры, значение `x:Class` не определено в службах XAML .NET Framework. Это происходит потому не соответствует модели программирования, которая разметки и вспомогательного кода являются подключения XAML служб XAML .NET Framework. Дополнительные применения `x:Class` директивы могут реализовываться конкретными платформами, которые используют модели программирования или модели приложений для определения способа соединения разметки XAML и на основе CLR кода. Каждая платформа может иметь собственные действия построения, включающие некоторое поведение или отдельные компоненты, которые должны быть включены в среде построения. Внутри платформы действия построения могут различаться в зависимости от конкретного языка среды CLR, который используется для кода.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>x: Class в модели программирования WPF  
 В приложениях WPF и модели приложения WPF `x:Class` можно объявить как атрибут для любого элемента, который является корнем файла XAML и компилируется (где XAML включен в проект приложения WPF с `Page` действие построения), или для < C4 настроек <xref:System.Windows.Application>  корневой в определении приложения скомпилированного приложения WPF. Объявление `x:Class` на элемент, отличный от корня страницы или корневой каталог приложения, или в файле WPF XAML, который не компилируется, приводит к ошибке времени компиляции, в разделе [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] и [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] компилятора XAML в WPF. Сведения о других аспектах `x:Class` обработке в WPF см. в разделе [кода и XAML в WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>x: Class для Windows Workflow Foundation  
 Для Windows Workflow Foundation `x:Class` именует класс пользовательского действия, составленного полностью в XAML, а также имена разделяемом классе страницу XAML для конструктора действий с выделенным кодом.  
  
## <a name="silverlight-usage-notes"></a>Примечания об использовании Silverlight  
 `x:Class`для Silverlight задокументирован отдельно. Дополнительные сведения см. в разделе [пространства имен XAML (x:) Языковые возможности (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>См. также  
 [Директива x:Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)  
 [Код XAML и пользовательские классы для WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [Директива x:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md)  
 [Типы, перенесенные из WPF в System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)

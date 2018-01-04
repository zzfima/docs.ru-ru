---
title: "Директива x:Members"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e76f539e713f3d21751de18c86cc2dcebf99f570
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="xmembers-directive"></a>Директива x:Members
Содержит набор элементов, определенные в разметке, которые применяются к x: Class родительского элемента.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`className`|Имя класса резервирования или разделяемого класса для рабочей среды XAML. См. заметки.|  
|`oneOrMoreMembers`|Один или несколько элементов объектов, представляющих определения элементов. Как правило, это `x:Property` элементов объекта. См. заметки.|  
  
## <a name="remarks"></a>Примечания  
 В реализации служб XAML .NET Framework нет класса резервирования или базовой реализацией члена для `x:Members`. `x:Members`— это специальные элемент XAML, который могут существовать как член с любым типом. В потоке узлов XAML `x:Members` представляется как элемент с именем `Members`, из пространства имен XAML языка XAML. Элемент `Members` содержит универсальный список только для чтения из `Member` объектов. В обычной разметке отдельных элементов задаются в виде `x:Property` свойств элементов. `x:Property`Это более точный тип специально для свойств типов и может быть назначен `x:Member`. Дополнительные сведения см. в разделе [директива x: Property](../../../docs/framework/xaml-services/x-property-directive.md).  
  
 Для поддержки практического использования `x:Members` как средства указания определений членов в разметке эти члены должны быть связаны с классом, который может быть изменен. Предполагаемая модель состоит в том, что `x:Members` существует в качестве члена типа, указывающего `x:Class`. Однако механизм для сопоставления типов и членов или для создания определений динамических членов не поддерживается на уровне служб XAML .NET Framework. Это отводится отдельным платформам, имеющим модели приложений, поддерживающие определения членов из XAML. Как правило, для поддержки этой функции требуются действия MSBUILD при построении, которые компилируют разметку XAML и либо интегрируют его с выделенным кодом, либо создают чистые сборки из XAML.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>x: Members для Windows Workflow Foundation  
 Для Windows Workflow Foundation `x:Members` содержит элементы, пользовательские действия, составленного полностью в XAML или XAML — определенные динамические члены для конструктора действий с выделенным кодом. `x:Class` также должен быть указан в корневом элементе рабочей среды XAML. Это не является обязательным на уровне служб XAML .NET Framework, но становится обязательным при загрузке рабочей среды XAML с помощью действий MSBUILD при построении, которые поддерживают пользовательские действия и Windows Workflow Foundation XAML в целом. `x:Members`должен быть первым дочерним элементом в разметке элемента объекта, который объявляет `x:Class`.

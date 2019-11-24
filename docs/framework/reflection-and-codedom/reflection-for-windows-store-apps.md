---
title: Отражение в .NET Framework для приложений для Магазина Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection, Windows Store apps
- .NET for Windows Store apps, TypeInfo class
ms.assetid: 0d07090c-9b47-4ecc-81d1-29d539603c9b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9aaec282fda0a038d14f3a0cd57e1a8a2855f2ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448143"
---
# <a name="reflection-in-the-net-framework-for-windows-store-apps"></a>Отражение в .NET Framework для приложений для Магазина Windows

Starting with the .NET Framework 4.5, the .NET Framework includes a set of reflection types and members for use in Windows 8.x Store apps. These types and members are available in the full .NET Framework as well as in the .NET for Windows Store apps. В этом документе описаны основные отличия между ними и их аналогами в платформе .NET Framework версии 4 и более ранних версий.  
  
 If you are creating a Windows 8.x Store app, you must use the reflection types and members in the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]. Эти типы и члены также доступны, но не обязательны, для использования в классических приложениях, поэтому можно использовать один и тот же код для обоих типов приложений.  
  
## <a name="typeinfo-and-assembly-loading"></a>TypeInfo и загрузка сборок  
 В [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] класс <xref:System.Reflection.TypeInfo> содержит некоторые возможности класса <xref:System.Type> .NET Framework 4. Объект <xref:System.Type> представляет собой ссылку на определение типа, а объект <xref:System.Reflection.TypeInfo> представляет само определение типа. Это позволяет управлять объектами <xref:System.Type> без обязательной загрузки средой выполнения сборки, на которую они ссылаются. Получение связанного объекта <xref:System.Reflection.TypeInfo> принудительно загружает сборку.  
  
 Класс <xref:System.Reflection.TypeInfo> содержит множество членов, доступных в классе <xref:System.Type>, а многие свойства отражения в [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] возвращают коллекции объектов <xref:System.Reflection.TypeInfo>. Чтобы получить объект <xref:System.Reflection.TypeInfo> из объекта <xref:System.Type>, используйте метод <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>.  
  
## <a name="query-methods"></a>Методы запросов  
 В [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] используются свойства отражения, которые возвращают коллекции <xref:System.Collections.Generic.IEnumerable%601> вместо методов, возвращающих массивы. Контексты отражения могут реализовывать отложенный обход этих коллекций для больших сборок или типов.  
  
 Свойства отражения возвращают только методы, объявленные в указанном объекте, а не обходят дерево наследования. Кроме того, они не используют параметры <xref:System.Reflection.BindingFlags> для фильтрации. Фильтрация выполняется в коде пользователя с помощью запросов LINQ к возвращаемым коллекциям. Для объектов отражения, создаваемых средой (например, как результат `typeof(Object)`), обход дерева наследования лучше выполнять с помощью вспомогательных методов класса <xref:System.Reflection.RuntimeReflectionExtensions>. Потребители объектов из настроенных контекстов отражения не могут использовать эти методы и должны сами выполнять обход дерева наследования.  
  
## <a name="restrictions"></a>Ограничения  
 In a Windows 8.x Store app, access to some .NET Framework types and members is restricted. Например, нельзя вызывать методы .NET Framework, не входящие в [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], с помощью объекта <xref:System.Reflection.MethodInfo>. In addition, certain types and members that are not considered safe within the context of a Windows 8.x Store app are blocked, as are <xref:System.Runtime.InteropServices.Marshal> and <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal> members. Это ограничение влияет только на типы и члены .NET Framework; свой код или сторонний код можно вызывать как обычно.  
  
## <a name="example"></a>Пример  
 В этом примере с использованием типов и членов отражения в [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] извлекаются методы и свойства типа <xref:System.Globalization.Calendar>, включая унаследованные методы и свойства. To run this code, paste it into the code file for a Windows 8.x Store page that contains a <xref:Windows.UI.Xaml.Controls.TextBlock?displayProperty=nameWithType> control named `textblock1` in a project named Reflection. При вставке этого кода в проект с другим именем просто убедитесь, что имя пространства имен соответствует вашему проекту.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Отражение](reflection.md)

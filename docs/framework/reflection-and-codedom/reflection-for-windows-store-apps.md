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
ms.openlocfilehash: 192ac28610f596bc6b6f4ebf1c80962ab2d71cbf
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46539269"
---
# <a name="reflection-in-the-net-framework-for-windows-store-apps"></a>Отражение в .NET Framework для приложений для Магазина Windows
Начиная с версии [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], платформа .NET Framework включает набор типов и членов отражения для использования в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Эти типы и члены доступны в полной версии платформы .NET Framework, а также в [.NET для приложений Магазина Windows](https://go.microsoft.com/fwlink/?LinkID=225700). В этом документе описаны основные отличия между ними и их аналогами в платформе .NET Framework версии 4 и более ранних версий.  
  
 При разработке приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] необходимо использовать типы и члены отражения в [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]. Эти типы и члены также доступны, но не обязательны, для использования в классических приложениях, поэтому можно использовать один и тот же код для обоих типов приложений.  
  
## <a name="typeinfo-and-assembly-loading"></a>TypeInfo и загрузка сборок  
 В [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] класс <xref:System.Reflection.TypeInfo> содержит некоторые возможности класса <xref:System.Type> .NET Framework 4. Объект <xref:System.Type> представляет собой ссылку на определение типа, а объект <xref:System.Reflection.TypeInfo> представляет само определение типа. Это позволяет управлять объектами <xref:System.Type> без обязательной загрузки средой выполнения сборки, на которую они ссылаются. Получение связанного объекта <xref:System.Reflection.TypeInfo> принудительно загружает сборку.  
  
 Класс <xref:System.Reflection.TypeInfo> содержит множество членов, доступных в классе <xref:System.Type>, а многие свойства отражения в [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] возвращают коллекции объектов <xref:System.Reflection.TypeInfo>. Чтобы получить объект <xref:System.Reflection.TypeInfo> из объекта <xref:System.Type>, используйте метод <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>.  
  
## <a name="query-methods"></a>Методы запросов  
 В [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] используются свойства отражения, которые возвращают коллекции <xref:System.Collections.Generic.IEnumerable%601> вместо методов, возвращающих массивы. Контексты отражения могут реализовывать отложенный обход этих коллекций для больших сборок или типов.  
  
 Свойства отражения возвращают только методы, объявленные в указанном объекте, а не обходят дерево наследования. Кроме того, они не используют параметры <xref:System.Reflection.BindingFlags> для фильтрации. Фильтрация выполняется в коде пользователя с помощью запросов LINQ к возвращаемым коллекциям. Для объектов отражения, создаваемых средой (например, как результат `typeof(Object)`), обход дерева наследования лучше выполнять с помощью вспомогательных методов класса <xref:System.Reflection.RuntimeReflectionExtensions>. Потребители объектов из настроенных контекстов отражения не могут использовать эти методы и должны сами выполнять обход дерева наследования.  
  
## <a name="restrictions"></a>Ограничения  
 В приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] доступ к некоторым типам и членам .NET Framework ограничен. Например, нельзя вызывать методы .NET Framework, не входящие в [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], с помощью объекта <xref:System.Reflection.MethodInfo>. Кроме того, заблокированы некоторые типы и члены, которые не считаются безопасными в контексте приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], а также члены <xref:System.Runtime.InteropServices.Marshal> и <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal>. Это ограничение влияет только на типы и члены .NET Framework; свой код или сторонний код можно вызывать как обычно.  
  
## <a name="example"></a>Пример  
 В этом примере с использованием типов и членов отражения в [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] извлекаются методы и свойства типа <xref:System.Globalization.Calendar>, включая унаследованные методы и свойства. Чтобы запустить этот код, вставьте его в файл кода для страницы [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], содержащей элемент управления [Windows.UI.Xaml.Controls.Textblock](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) с именем `textblock1`. При вставке этого кода в проект с другим именем просто убедитесь, что имя пространства имен соответствует вашему проекту.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Отражение](../../../docs/framework/reflection-and-codedom/reflection.md)  
 [Поддерживаемые API .NET для приложений Магазина Windows](https://go.microsoft.com/fwlink/?LinkID=225700)

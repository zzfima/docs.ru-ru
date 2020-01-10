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
ms.openlocfilehash: 42bcfd4a1adc66511a1183807c09e77d1448c754
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715886"
---
# <a name="reflection-in-the-net-framework-for-windows-store-apps"></a>Отражение в .NET Framework для приложений для Магазина Windows

Начиная с .NET Framework 4,5, .NET Framework включает набор типов отражения и членов для использования в приложениях Магазина Windows 8. x. Эти типы и члены доступны в полной версии платформы .NET Framework, а также в .NET для приложений Магазина Windows. В этом документе описаны основные отличия между ними и их аналогами в платформе .NET Framework версии 4 и более ранних версий.  
  
 При создании приложения Магазина Windows 8. x необходимо использовать типы отражения и члены в приложениях для магазина .NET для Windows 8. x. Эти типы и члены также доступны, но не обязательны, для использования в классических приложениях, поэтому можно использовать один и тот же код для обоих типов приложений.  
  
## <a name="typeinfo-and-assembly-loading"></a>TypeInfo и загрузка сборок  
 В приложениях для магазина .NET для Windows 8. x класс <xref:System.Reflection.TypeInfo> содержит некоторые функции класса .NET Framework 4 <xref:System.Type>. Объект <xref:System.Type> представляет собой ссылку на определение типа, а объект <xref:System.Reflection.TypeInfo> представляет само определение типа. Это позволяет управлять объектами <xref:System.Type> без обязательной загрузки средой выполнения сборки, на которую они ссылаются. Получение связанного объекта <xref:System.Reflection.TypeInfo> принудительно загружает сборку.  
  
 <xref:System.Reflection.TypeInfo> содержит множество членов, доступных в <xref:System.Type>, а многие свойства отражения в .NET для приложений Магазина Windows 8. x возвращают коллекции объектов <xref:System.Reflection.TypeInfo>. Чтобы получить объект <xref:System.Reflection.TypeInfo> из объекта <xref:System.Type>, используйте метод <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>.  
  
## <a name="query-methods"></a>Методы запросов  
 В приложениях для магазина .NET для Windows 8. x используются свойства отражения, которые возвращают <xref:System.Collections.Generic.IEnumerable%601> коллекции вместо методов, возвращающих массивы. Контексты отражения могут реализовывать отложенный обход этих коллекций для больших сборок или типов.  
  
 Свойства отражения возвращают только методы, объявленные в указанном объекте, а не обходят дерево наследования. Кроме того, они не используют параметры <xref:System.Reflection.BindingFlags> для фильтрации. Фильтрация выполняется в коде пользователя с помощью запросов LINQ к возвращаемым коллекциям. Для объектов отражения, создаваемых средой (например, как результат `typeof(Object)`), обход дерева наследования лучше выполнять с помощью вспомогательных методов класса <xref:System.Reflection.RuntimeReflectionExtensions>. Потребители объектов из настроенных контекстов отражения не могут использовать эти методы и должны сами выполнять обход дерева наследования.  
  
## <a name="restrictions"></a>Ограничения  
 В приложении для Магазина Windows 8. x доступ к некоторым типам .NET Framework и членам ограничен. Например, нельзя вызывать методы .NET Framework, не входящие в .NET для приложений Магазина Windows 8. x, с помощью объекта <xref:System.Reflection.MethodInfo>. Кроме того, блокируются некоторые типы и члены, которые не считаются безопасными в контексте приложения Магазина Windows 8. x, как и <xref:System.Runtime.InteropServices.Marshal> и <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal> членов. Это ограничение влияет только на типы и члены .NET Framework; свой код или сторонний код можно вызывать как обычно.  
  
## <a name="example"></a>Пример  
 В этом примере используются типы отражения и члены в приложениях Магазина .NET для Windows 8. x для получения методов и свойств типа <xref:System.Globalization.Calendar>, включая унаследованные методы и свойства. Чтобы выполнить этот код, вставьте его в файл кода для страницы хранилища Windows 8. x, которая содержит элемент управления <xref:Windows.UI.Xaml.Controls.TextBlock?displayProperty=nameWithType> с именем `textblock1` в проекте с именем Reflection. При вставке этого кода в проект с другим именем просто убедитесь, что имя пространства имен соответствует вашему проекту.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также:

- [Отражение](reflection.md)

---
title: Практическое руководство. Загрузка сборок в домен приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
ms.openlocfilehash: c560e2c5858de67442ccbcd18c8f92b142cc178d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119893"
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a>Практическое руководство. Загрузка сборок в домен приложения
Существует несколько способов загрузки сборки в домен приложения. Рекомендуется использовать метод <xref:System.Reflection.Assembly.Load%2A> `static` (`Shared` в Visual Basic) класса <xref:System.Reflection.Assembly?displayProperty=nameWithType>. Другими способами загрузки сборок являются:  
  
- Метод <xref:System.Reflection.Assembly.LoadFrom%2A> класса <xref:System.Reflection.Assembly> загружает сборку, заданную расположением ее файла. При загрузке сборок с помощью этого метода используется другой контекст загрузки.  
  
- Методы <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> и <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> загружают сборку в контекст, предназначенный только для отражения. Сборки, загруженные в этом контексте, могут быть проверены, но не выполнены, позволяя производить проверку сборок, предназначенных для других платформ. См. раздел [Практическое руководство. Загрузка сборок в контекст, предназначенный только для отражения](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
> [!NOTE]
> Контекст только для отражения впервые появился в платформе .NET Framework версии 2.0.  
  
- Такие методы, как <xref:System.AppDomain.CreateInstance%2A> и <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> класса <xref:System.AppDomain> могут загружать сборки в домен приложения.  
  
- Метод <xref:System.Type.GetType%2A> класса <xref:System.Type> может загружать сборки.  
  
- Метод <xref:System.AppDomain.Load%2A> класса <xref:System.AppDomain?displayProperty=nameWithType> может загружать сборки, но в основном он используется для COM-взаимодействия. Его не следует использовать для загрузки сборок в домен приложения, отличный от домена приложения, из которого он вызывается.  
  
> [!NOTE]
> Начиная с платформы .NET Framework версии 2.0, среда выполнения не загружает сборки, которые были скомпилированы версиями платформы .NET Framework, чей номер версии выше, чем у текущей среды выполнения. Это применимо к сочетанию основного и дополнительного номеров для номера версии.  
  
 Можно определить способ, которым JIT-скомпилированный код из загруженных сборок будет распределен между доменами приложений. Дополнительные сведения см. в статье [Домены приложений и сборки](application-domains.md#application-domains-and-assemblies).  
  
## <a name="example"></a>Пример  
 Следующий код загружает сборку с именем "example.exe" или "example.dll" в текущий домен приложения, получает тип с именем `Example` из сборки, получает метод без параметров `MethodA` для этого типа и выполняет этот метод. Полное описание получения сведений из загруженной сборки см. в разделе [Динамическая загрузка и использование типов](../reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- [Программирование с использованием доменов приложений](application-domains.md#programming-with-application-domains)
- [Отражение](../reflection-and-codedom/reflection.md)
- [Использование доменов приложений](use.md)
- [Практическое руководство. Загрузка сборок в контекст, предназначенный только для отражения](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)
- [Домены приложений и сборки](application-domains.md#application-domains-and-assemblies)

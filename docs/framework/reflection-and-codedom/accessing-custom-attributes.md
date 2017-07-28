---
title: "Доступ к пользовательским атрибутам | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fbbc83b6aafdd5f2cbf554de66bc19f49d635aff
ms.contentlocale: ru-ru
ms.lasthandoff: 06/02/2017

---
# <a name="accessing-custom-attributes"></a>Доступ к пользовательским атрибутам
После того как с элементами программы связаны атрибуты, можно использовать отражение для проверки их существования и получения значений. В .NET Framework версии 1.0 и 1.1 пользовательские атрибуты проверяются в контексте выполнения. Платформа .NET Framework версии 2.0 предоставляет новый контекст загрузки — контекст только для отражения, используемый для проверки кода, который не может быть загружен для выполнения.  
  
## <a name="the-reflection-only-context"></a>Контекст только для отражения  
 Код, загруженный в контекст только для отражения, не может быть выполнен. Это означает, что экземпляры пользовательских атрибутов не могут быть созданы, потому что это потребует выполнения соответствующих конструкторов. Чтобы загрузить и просмотреть пользовательские атрибуты в контексте только для отражения, используйте класс <xref:System.Reflection.CustomAttributeData>. Экземпляры этого класса можно получить посредством использования допустимой перегрузки статического метода <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName>. См. раздел [Практическое руководство. Загрузка сборок в контекст, предназначенный только для отражения](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
## <a name="the-execution-context"></a>Контекст выполнения  
 Основные методы отражения, используемые для запроса атрибутов в контексте выполнения — это <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName> и <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>.  
  
 Возможность доступа к пользовательскому атрибуту проверяется относительно сборки, с которой он связан. Это эквивалентно проверке того, может ли метод типа в сборке, с которой связан атрибут, вызвать конструктор этого атрибута.  
  
 Такие методы, как <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=fullName>, проверяют видимость и доступность аргумента типа. Получить атрибут определенного пользователем типа с помощью метода **GetCustomAttributes** может только код в сборке, содержащей этот тип.  
  
 В следующем примере C# показан типичный способ задания пользовательского атрибута. Этот пример иллюстрирует модель отражения пользовательских атрибутов во время выполнения.  
  
```  
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 Если среда выполнения пытается получить пользовательские атрибуты для открытого типа пользовательского атрибута <xref:System.ComponentModel.DescriptionAttribute>, присоединенного к методу **GetLanguage**, она выполняет следующие действия:  
  
1.  Среда выполнения проверяет, является ли аргумент типа **DescriptionAttribute** для метода **Type.GetCustomAttributes**(тип *type*) и, следовательно, видимым и доступным.  
  
2.  Среда выполнения проверяет, является ли определяемый пользователем тип **MyDescriptionAttribute**, производный от **DescriptionAttribute**, видимым и доступным в сборке **System.Web.DLL**, в которой он присоединен к методу **GetLanguage**().  
  
3.  Среда выполнения проверяет, является ли конструктор атрибута **MyDescriptionAttribute** видимым и доступным в сборке **System.Web.DLL**.  
  
4.  Среда выполнения вызывает конструктор атрибута **MyDescriptionAttribute** с параметрами пользовательского атрибута и возвращает в вызывающий код новый объект.  
  
 Модель отражения пользовательских атрибутов может создать экземпляры определенного пользователем типа вне сборки, в которой этот тип определен. Возникает та же ситуация, что и в случае элементов в системной библиотеке среды выполнения, которые возвращают экземпляры определяемых пользователем типов, как, например, метод <xref:System.Type.GetMethods%2A?displayProperty=fullName> возвращает массив объектов **RuntimeMethodInfo**. Чтобы клиент не смог получить сведения о типе атрибута, определенном пользователем, следует описать элементы этого типа как неоткрытые.  
  
 В следующем примере показан простейший способ использования отражения для получения доступа к пользовательским атрибутам.  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)] [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)] [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [Просмотр сведений о типах](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Соображения о безопасности для отражения](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)

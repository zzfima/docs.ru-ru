---
title: Повышение эффективности отладки с помощью атрибутов просмотра отладчика
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- debugger, display attributes
- DebuggerTypeProxyAttribute attribute
- debugging [.NET Framework], debugger display attributes
- DebuggerDisplayAttribute attribute
- display attributes for debugger
- DebuggerBrowsableAttribute attribute
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
ms.openlocfilehash: ca118bffb045a0e7e3a5084916a0ff8020ebda90
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216489"
---
# <a name="enhancing-debugging-with-the-debugger-display-attributes"></a>Повышение эффективности отладки с помощью атрибутов просмотра отладчика

С помощью атрибутов просмотра отладчика разработчик типа может определить параметры отображения типа в отладчике, что позволяет лучше описать его поведение во время выполнения. Кроме того, пользователи, не знакомые с соответствующим исходным кодом, могут применить на уровне сборки атрибуты просмотра отладчика, предоставляющие свойство `Target`. Атрибут <xref:System.Diagnostics.DebuggerDisplayAttribute> определяет, как тип или член отображается в окнах переменных отладчика. Атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute> определяет, отображается ли поле или свойство в окнах переменных отладчика, и каким образом это реализуется. Атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> указывает прокси (заменяющий тип) для типа и меняет способ отображения типа в окнах отладчика. При просмотре переменной, имеющей прокси-сервер, или замены типа прокси-сервер заменяет исходный тип в окне отображения отладчика. Окно переменных отладчика отображает только открытые члены прокси-типа. Закрытые члены не отображаются.  
  
## <a name="using-the-debuggerdisplayattribute"></a>Использование атрибута DebuggerDisplayAttribute  

Конструктор <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> имеет один аргумент, определяющий строку, которая должна отображаться в столбце "Значение" для экземпляров типа. Эта строка может содержать фигурные скобки ({ и }). Текст, заключенный в фигурные скобки, вычисляется как выражение. Например, при нажатии на значок плюса (+) для развертывания окна просмотра отладчика для экземпляра `MyHashtable` следующий код C# отображает "Count = 4".  

```csharp
[DebuggerDisplay("Count = {count}")]
class MyHashtable
{
    public int count = 4;
}
```

Атрибуты, применяемые к свойствам, на которые есть ссылки в выражении, не обрабатываются. Компилятор C# поддерживает только общие выражения с неявным доступом к этой ссылке для текущего экземпляра конечного типа. Выражение ограничено и не имеет доступа к псевдонимам, локальным переменным или указателям. В C# можно использовать общее выражение в скобках, которое имеет неявный доступ к указателю `this` только для текущего экземпляра конечного типа.

Например, если в объекте C# имеется переопределенный метод `ToString()`, отладчик будет вызывать переопределенный метод и отображать возвращаемый им результат, а не имя типа `{<typeName>}.`. Таким образом, если метод `ToString()` переопределен, нет необходимости использовать <xref:System.Diagnostics.DebuggerDisplayAttribute>. Если используется и то и другое, то атрибут <xref:System.Diagnostics.DebuggerDisplayAttribute> будет иметь более высокий приоритет по отношению к переопределению `ToString()`.

## <a name="using-the-debuggerbrowsableattribute"></a>Использование атрибута DebuggerBrowsableAttribute
 Применяя атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute> к полю или свойству, можно указать, как они будут отображаться в окне отладчика. Конструктор этого атрибута принимает одно из значений перечисления <xref:System.Diagnostics.DebuggerBrowsableState>, которое задает одно из следующих состояний:

- <xref:System.Diagnostics.DebuggerBrowsableState.Never> указывает, что член не отображается в окне данных.  Например, если применить это значение к полю <xref:System.Diagnostics.DebuggerBrowsableAttribute>, это поле будет удалено из иерархии и не будет отображаться при развертывании включающего типа путем нажатия кнопки плюса (+) для экземпляра типа.

- <xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> указывает, что член отображается, но по умолчанию не развернут.  Это поведение по умолчанию.

- <xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> указывает, что сам член не отображается, однако если это массив или коллекция, то выводятся составляющие его объекты.

> [!NOTE]
> Атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute> не поддерживается в Visual Basic на платформе .NET Framework версии 2.0.

В следующем примере кода показано, как использовать атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute>, чтобы отключить отображение следующего за ним свойства в окне отладки для класса.

```csharp
[DebuggerBrowsable(DebuggerBrowsableState.Never)]
public static string y = "Test String";
```

## <a name="using-the-debuggertypeproxy"></a>Использование атрибута DebuggerTypeProxy
 Атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> позволяет существенным образом изменить представление отладки для типа, не изменяя при этом сам тип. Атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> задает прокси-тип отображения для типа, позволяя разработчику настроить представление этого типа.  Как и <xref:System.Diagnostics.DebuggerDisplayAttribute>, этот атрибут можно использовать на уровне сборки. В этом случае свойство <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> задает тип, для которого будет использоваться прокси. Этот атрибут рекомендуется использовать для частного вложенного типа, входящего в тип, к которому применен этот атрибут.  При отображении типа вычислитель выражений, поддерживающий средства просмотра типов, проверяет наличие этого атрибута. Если он найден, вычислитель выражений заменяет прокси-тип отображения на тип, к которому применен этот атрибут.

 Если атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> задан, окно переменных отладчика отображает только открытые члены прокси-типа. Закрытые члены не отображаются. При использовании атрибутов просмотра поведение окна данных не изменяется.

 Чтобы исключить потери производительности, атрибуты прокси-типа отображения обрабатываются только тогда, когда объект развертывается с помощью значка плюса (+) рядом с типом в окне данных или посредством атрибута <xref:System.Diagnostics.DebuggerBrowsableAttribute> в приложении. В связи с этим не рекомендуется применять атрибуты к типам отображения. Атрибуты можно и нужно применять в основной части типа отображения.

 В следующем примере кода показано использование атрибута <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, указывающего тип, который будет использоваться в качестве прокси-типа отображения для отладчика.

```csharp
[DebuggerTypeProxy(typeof(HashtableDebugView))]
class MyHashtable : Hashtable
{
    private const string TestString =
        "This should not appear in the debug window.";

    internal class HashtableDebugView
    {
        private Hashtable hashtable;
        public const string TestStringProxy =
            "This should appear in the debug window.";

        // The constructor for the type proxy class must have a
        // constructor that takes the target type as a parameter.
        public HashtableDebugView(Hashtable hashtable)
        {
            this.hashtable = hashtable;
        }
    }
}
```

## <a name="example"></a>Пример

### <a name="description"></a>Описание

Следующий пример кода можно просмотреть в Visual Studio, чтобы просмотреть результаты применения атрибутов <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute>и <xref:System.Diagnostics.DebuggerTypeProxyAttribute>.

### <a name="code"></a>Код

[!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
[!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
[!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]

## <a name="see-also"></a>См. также:

- <xref:System.Diagnostics.DebuggerDisplayAttribute>
- <xref:System.Diagnostics.DebuggerBrowsableAttribute>
- <xref:System.Diagnostics.DebuggerTypeProxyAttribute>

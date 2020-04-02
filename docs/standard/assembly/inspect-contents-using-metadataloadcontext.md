---
title: Практическое руководство. Проверка содержимого сборки с помощью MetadataLoadContext
description: Сведения об использовании MetadataLoadContext, API, позволяющее загружать сборки .NET для целей проверки.
author: MSDN-WhiteKnight
ms.date: 03/10/2020
ms.technology: dotnet-standard
ms.openlocfilehash: a782b2db4fb62cfaedaa6768e2131bda6bec864c
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80229275"
---
# <a name="how-to-inspect-assembly-contents-using-metadataloadcontext"></a>Практическое руководство. Проверка содержимого сборки с помощью MetadataLoadContext

API отражения в .NET по умолчанию позволяет разработчикам проверять содержимое сборок, загруженных в основной контекст выполнения. Однако иногда невозможно загрузить сборку в контекст выполнения, например, если она была скомпилирована для другой архитектуры платформы или процессора либо если это [базовая сборка](reference-assemblies.md). API <xref:System.Reflection.MetadataLoadContext?displayProperty=fullName> позволяет загружать и проверять такие сборки. Сборки, загруженные в <xref:System.Reflection.MetadataLoadContext>, обрабатываются только как метаданные, то есть вы можете проверять типы в сборке, но не выполнять код, содержащийся в ней. В отличие от основного контекста выполнения <xref:System.Reflection.MetadataLoadContext> не загружает зависимости из текущего каталога автоматически. Вместо этого используется пользовательская логика привязки, предоставляемая <xref:System.Reflection.MetadataAssemblyResolver>, переданной в нее.

## <a name="prerequisites"></a>Предварительные требования

Чтобы использовать <xref:System.Reflection.MetadataLoadContext>, установите пакет NuGet [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext). Она поддерживается в любой целевой платформе, совместимой с .NET Standard 2.0, например .NET Core 2.0 или .NET Framework 4.6.1.

## <a name="create-metadataassemblyresolver-for-metadataloadcontext"></a>Создание MetadataAssemblyResolver для MetadataLoadContext

Создание <xref:System.Reflection.MetadataLoadContext> требует предоставления экземпляра <xref:System.Reflection.MetadataAssemblyResolver>. Самый простой способ указать, что он использует <xref:System.Reflection.PathAssemblyResolver>, который разрешает сборки из заданной коллекции строк пути сборки. Эта коллекция, помимо сборок, которые необходимо проверить напрямую, также должна включать все необходимые зависимости. Например, для чтения настраиваемого атрибута, расположенного во внешней сборке, следует включить эту сборку, иначе будет вызвано исключение. В большинстве случаев следует включать по крайней мере *основную сборку*, то есть сборку, содержащую встроенные системные типы, такие как <xref:System.Object?displayProperty=nameWithType>. В следующем коде показано, как создать <xref:System.Reflection.PathAssemblyResolver> с помощью коллекции, состоящей из проверенной сборки и основной сборки текущей среды выполнения:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CoreAssembly)]

Если требуется доступ ко всем типам BCL, в коллекцию можно включить все сборки среды выполнения. В следующем коде показано, как создать <xref:System.Reflection.PathAssemblyResolver> с помощью коллекции, состоящей из проверенной сборки и все сборки текущей среды выполнения:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#RuntimeAssemblies)]

## <a name="create-metadataloadcontext"></a>Создание MetadataLoadContext

Чтобы создать <xref:System.Reflection.MetadataLoadContext>, вызовите его конструктор <xref:System.Reflection.MetadataLoadContext.%23ctor%28System.Reflection.MetadataAssemblyResolver%2CSystem.String%29>, передав ранее созданный <xref:System.Reflection.MetadataAssemblyResolver> в качестве первого параметра и основное имя сборки в качестве второго параметра. Имя основной сборки можно опустить, в этом случае конструктор попытается использовать имена по умолчанию: "mscorlib", "System.Runtime" или "netstandard".

После создания контекста в него можно загрузить сборки с помощью таких методов, как <xref:System.Reflection.MetadataLoadContext.LoadFromAssemblyPath%2A>. Все API отражения можно использовать в загруженных сборках, за исключением тех, которые используют выполнение кода. Метод <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A> требует выполнения конструкторов, поэтому, если необходимо исследовать пользовательские атрибуты в <xref:System.Reflection.MetadataLoadContext>, вместо этого следует использовать метод <xref:System.Reflection.MemberInfo.GetCustomAttributesData%2A>.

Следующий пример кода создает <xref:System.Reflection.MetadataLoadContext>, загружает в него сборку и выводит атрибуты сборки в консоль:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CreateContext)]

## <a name="example"></a>Пример

Пример полного кода см. [Проверка содержимого сборки с помощью MetadataLoadContext](https://docs.microsoft.com/samples/dotnet/samples/inspect-assembly-contents-using-metadataloadcontext/).

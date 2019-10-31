---
title: Пошаговое руководство. Выпуск кода в сценариях частичного доверия
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection emit, anonymously hosted dynamic methods
- partial trust, reflection
- partial trust, emitting dynamic methods
- reflection emit, partial trust scenarios
- anonymously hosted dynamic methods [.NET Framework]
- emitting dynamic assemblies,partial trust scenarios
- reflection emit, dynamic methods
- dynamic methods
ms.assetid: c45be261-2a9d-4c4e-9bd6-27f0931b7d25
ms.openlocfilehash: fd420c9754494b95c55df403edec87743572db03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129996"
---
# <a name="walkthrough-emitting-code-in-partial-trust-scenarios"></a>Пошаговое руководство. Выпуск кода в сценариях частичного доверия

При порождении отражения для полного или частичного доверия используется одинаковый набор интерфейсов API, но для некоторых функциональных возможностей требуются особые разрешения в коде с частичным доверием. Кроме того, в порождении отражения имеется функциональная возможность, анонимно размещенные динамические методы, которые предназначены для использования при частичном доверии и в прозрачных с точки зрения безопасности сборках.

> [!NOTE]
> В версиях, предшествовавших .NET Framework 3.5, для порождения кода требовалось разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType>. Это разрешение включено по умолчанию в именованные наборы разрешений `FullTrust` и `Intranet`, но отсутствует в наборе разрешений `Internet`. Поэтому библиотека может использоваться при частичном доверии, только если у нее был атрибут <xref:System.Security.SecurityCriticalAttribute> и она выполнила метод <xref:System.Security.PermissionSet.Assert%2A> для <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>. Такие библиотеки требуют тщательной проверки безопасности, так как ошибки в коде могут стать причиной уязвимости. Платформа .NET Framework 3.5 позволяет создавать код в сценариях частичного доверия без предъявления каких-либо требований к безопасности, так как создание кода по сути не является привилегированной операцией. То есть созданный код имеет не больше разрешений, чем породившая его сборка. Это позволяет библиотекам порождать код, прозрачный с точки зрения безопасности, и устраняет необходимость в подтверждении <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>, что упрощает задачу написания безопасной библиотеки, так как тщательная проверка безопасности не нужна.

В данном пошаговом руководстве рассмотрены следующие задачи:

- [Настройка простой песочницы для проверки кода с частичным доверием](#Setting_up).

  > [!IMPORTANT]
  > Это простой способ поэкспериментировать с кодом с частичным доверием. Сведения о выполнении кода, поступившего из ненадежных расположений, см. в разделе [Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md).

- [Выполнение кода в доменах приложений с частичным доверием](#Running_code).

- [Использование анонимно размещенных динамических методов для порождения и выполнения кода при частичном доверии](#Using_methods).

Дополнительные сведения о порождении кода в сценариях с частичным доверием см. в разделе [Вопросы безопасности в порождаемом отражении](security-issues-in-reflection-emit.md).

Полный код, показанный в данных процедурах, см. в разделе [Пример](#Example) в конце этого руководства.

<a name="Setting_up"></a>

## <a name="setting-up-partially-trusted-locations"></a>Настройка расположений с частичным доверием

В следующих двух процедурах показано, как настроить расположения, из которых можно протестировать код с частичным доверием.

- В первой процедуре показано, как создать домен изолированного приложения, в котором код выполняется с интернет-доверием.

- Во второй процедуре показано, как добавить <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> в домен приложения с частичным доверием для разрешения доступа к конфиденциальным данным в сборках с тем же или меньшим доверием.

### <a name="creating-sandboxed-application-domains"></a>Создание доменов изолированных приложений

Чтобы создать домен приложения, в котором сборки будут выполняться при частичном доверии, необходимо указать набор разрешений, которые должны быть предоставлены сборкам, используя перегрузку метода <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> для создания домена приложения. Самым простым способом указания набора разрешений является получение именованного набора разрешений из политики безопасности.

В следующей процедуре создается домен изолированного приложения, в котором код будет выполняться при частичном доверии, для проверки сценариев, в которых порожденный код имеет доступ только к открытым членам открытых типов. В следующей процедуре показано, как добавить <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> для проверки сценариев, в которых порожденный код имеет доступ к закрытым типам и членам в сборках, которым предоставлены равнозначные или меньшие разрешения.

#### <a name="to-create-an-application-domain-with-partial-trust"></a>Создание домена приложения с частичным доверием

1. Создайте набор разрешений, которые следует предоставить сборкам в домене изолированного приложения. В этом случае используется набор разрешений зоны Интернета.

    [!code-csharp[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#2)]
    [!code-vb[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#2)]

2. Создайте объект <xref:System.AppDomainSetup> для инициализации домена приложения с помощью пути к приложению.

    > [!IMPORTANT]
    > Для простоты в этом примере кода используется текущая папка. Для выполнения кода, поступившего из Интернета, используйте отдельную папку для ненадежного кода, как описано в разделе [Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md).

    [!code-csharp[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#3)]
    [!code-vb[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#3)]

3. Создайте домен приложения, указав сведения о настройке домена приложения и набор правил для всех сборок, выполняющихся в домене приложения.

    [!code-csharp[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#5)]
    [!code-vb[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#5)]

    С помощью последнего параметра перегрузки метода <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> можно указать набор сборок, которым будет предоставлено полное доверие, вместо набора правил для домена приложения. Вам не нужно указывать сборки .NET Framework, используемые приложением, так как они находятся в глобальном кэше сборок. Сборки, находящиеся в глобальном кэше сборок, всегда имеют полное доверие. Этот параметр можно использовать для указания сборок со строгими именами, которые не находятся в глобальном кэше сборок.

### <a name="adding-restrictedmemberaccess-to-sandboxed-domains"></a>Добавление RestrictedMemberAccess к изолированным доменам

Ведущие приложения могут разрешать доступ анонимно размещенных динамических методов к конфиденциальным данным в сборках, уровень доверия которых не превышает уровень доверия сборки, порождающей код. Чтобы разрешить эту ограниченную возможность пропуска проверок видимости, выполняемых JIT-компилятором, ведущее приложение добавляет объект <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> (RMA) в набор правил.

Например, ведущее приложение может предоставить интернет-приложениям интернет-разрешения и RMA, так что интернет-приложение может породить код, который обращается к конфиденциальным данным в собственных сборках. Так как доступ ограничен сборками с таким же или меньшим доверием, веб-приложение не может обращаться к членам полностью доверенных сборок, например сборок .NET Framework.

> [!NOTE]
> Чтобы предотвратить повышение привилегий, при создании анонимно размещенных динамических методов включаются также сведения стека для порождающей сборки. При вызове метода проверяются сведения стека. Поэтому вызванный из полностью доверенного кода анонимно размещенный динамический метод все так же ограничен уровнем доверия порождающей сборки.

#### <a name="to-create-an-application-domain-with-partial-trust-plus-rma"></a>Создание домена приложения с частичным доверием и RMA

1. Создайте объект <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> (RMA) и используйте метод <xref:System.Security.PermissionSet.SetPermission%2A?displayProperty=nameWithType> для добавления разрешения в набор правил.

    [!code-csharp[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#7)]
    [!code-vb[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#7)]

    Метод <xref:System.Security.PermissionSet.AddPermission%2A> добавляет это разрешение в набор правил, если его там еще нет. Если разрешение уже включено в набор правил, указанные флаги добавляются к существующим разрешениям.

    > [!NOTE]
    > RMA — это функциональная возможность анонимно размещенных динамических методов. Если обычные динамические методы пропускают проверки видимости, выполняемые JIT-компилятором, порождаемый код требует полного доверия.

2. Создайте домен приложения, указав сведения о настройке домена приложения и набор правил.

    [!code-csharp[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#8)]
    [!code-vb[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#8)]

<a name="Running_code"></a>

## <a name="running-code-in-sandboxed-application-domains"></a>Выполнение кода в доменах изолированных приложений

В следующей процедуре объясняется, как определить класс с помощью методов, которые могут быть выполнены в домене приложения, как создать экземпляр класса в домене и как выполнить его методы.

#### <a name="to-define-and-execute-a-method-in-an-application-domain"></a>Определение и выполнение метода в домене приложения

1. Определите класс, производный от класса <xref:System.MarshalByRefObject>. Это позволит создавать экземпляры класса в других доменах приложений, а также вызывать методы за пределами домена приложения. Класс в этом примере назван `Worker`.

    [!code-csharp[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#10)]
    [!code-vb[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#10)]

2. Определите открытый метод, содержащий код, который следует выполнить. В этом примере в коде порождается простой динамический метод, создается делегат для выполнения этого метода и вызывается делегат.

    [!code-csharp[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#11)]
    [!code-vb[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#11)]

3. В основной программе получите отображаемое имя сборки. Это имя используется при создании экземпляров класса `Worker` в домене изолированного приложения.

    [!code-csharp[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#14)]
    [!code-vb[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#14)]

4. В основной программе создайте домен изолированного приложения, как описано в [первой процедуре](#Setting_up) этого пошагового руководства. Добавлять какие-либо разрешения в набор разрешений `Internet` не нужно, так как метод `SimpleEmitDemo` использует только открытые методы.

5. В основной программе создайте экземпляр класса `Worker` в домене изолированного приложения.

    [!code-csharp[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#12)]
    [!code-vb[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#12)]

    Метод <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> создает объект в целевом домене приложения и возвращает прокси, который может использоваться для вызова свойств и методов объекта.

    > [!NOTE]
    > При использовании этого кода в Visual Studio необходимо изменить имя класса для включения пространства имен. По умолчанию пространство имен носит имя проекта. Например, если проект называется PartialTrust, имя класса должно быть PartialTrust.Worker.

6. Добавьте код для вызова метода `SimpleEmitDemo`. Вызов маршалируется за пределы домена приложения, а код выполняется в изолированном домене приложения.

    [!code-csharp[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#13)]
    [!code-vb[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#13)]

<a name="Using_methods"></a>

## <a name="using-anonymously-hosted-dynamic-methods"></a>Использование анонимно размещенных динамических методов

Анонимно размещенные динамические методы связаны с прозрачной сборкой, предоставленной системой. Поэтому содержащийся в них код является прозрачным. С другой стороны, обычные динамические методы должны быть связаны с существующим модулем (указанным непосредственно или выведенным из связанного типа) и принимать от него уровень безопасности.

> [!NOTE]
> Единственный способ сопоставления динамического метода со сборкой, предоставляющей анонимное размещение, — это использование конструкторов, описанных в следующей процедуре. Невозможно явно указать модуль в анонимно размещающей сборке.

Обычные динамические методы имеют доступ к внутренним членам модуля, с которым они связаны, или к закрытым членам типа, с которым они связаны. Так как анонимно размещенные динамические методы изолированы от другого кода, они не имеют доступа к конфиденциальным данным. Но у них есть ограниченная возможность пропускать проверки видимости, выполняемые JIT-компилятором, для получения доступа к конфиденциальным данным. Эта возможность ограничивается сборками, уровень доверия которых не превышает уровень доверия сборки, породившей этот код.

Чтобы предотвратить повышение привилегий, при создании анонимно размещенных динамических методов включаются также сведения стека для порождающей сборки. При вызове метода проверяются сведения стека. Вызванный из полностью доверенного кода анонимно размещенный динамический метод все так же ограничен уровнем доверия породившей его сборки.

#### <a name="to-use-anonymously-hosted-dynamic-methods"></a>Использование анонимно размещенных динамических методов

- Создайте анонимно размещенный динамический метод с помощью конструктора, который не задает связанный модуль или тип.

  [!code-csharp[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#15)]
  [!code-vb[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#15)]

  Если анонимно размещенный динамический метод использует только открытые типы и методы, ему не требуется ограниченный доступ к членам и он может не пропускать проверки видимости, выполняемые JIT-компилятором.

  Специальных разрешений для порождения динамического метода не требуется, но порождаемый код нуждается в разрешениях, которые требуются для используемых в этом коде типов и методов. Например, если порожденный код вызывает метод, который получает доступ к файлу, необходимо разрешение <xref:System.Security.Permissions.FileIOPermission>. Если уровень доверия не включает это разрешение, при выполнении порожденного кода создается исключение безопасности. Приведенный здесь код порождает динамический метод, который использует только метод <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>. Поэтому код может быть выполнен в расположениях с частичным доверием.

- Кроме того, вы можете создать анонимно размещенный динамический метод с ограниченной возможностью пропуска проверок видимости, выполняемых JIT-компилятором, путем использования конструктора <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29> и указания значения `true` для параметра `restrictedSkipVisibility`.

  [!code-csharp[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#16)]
  [!code-vb[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#16)]

  Ограничение заключается в том, что анонимно размещенный динамический метод может получать доступ к конфиденциальным данным только в сборках, уровень доверия которых не превышает уровень доверия порождающей сборки. Например, если динамический метод выполняется с доверием Интернету, он может получить доступ к конфиденциальным данным в других сборках, которые также работают с доверием Интернету, но не может получить доступ к конфиденциальным данным сборок .NET Framework. Сборки .NET framework устанавливаются в глобальном кэше сборок и всегда имеют полное доверие.

  Анонимно размещенные динамические методы могут использовать эту ограниченную возможность пропуска проверок видимости, выполняемых JIT-компилятором, только в том случае, если ведущее приложение предоставляет разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>. Это разрешение требуется при вызове метода.

  > [!NOTE]
  > Сведения стека вызовов для порождающей сборки включаются при создании динамического метода. Поэтому запрос делается в отношении разрешений порождающей сборки, а не сборки, вызывающей метод. Это препятствует выполнению порожденного кода с повышенным уровнем разрешений.

  [Полный пример кода](#Example) в конце этого пошагового руководства служит для демонстрации использования ограниченного доступа к членам. Класс `Worker` содержит метод, который может создавать анонимно размещенные динамические методы с ограниченной возможностью пропускать проверки видимости или без нее, а в примере показан результат выполнения этого метода в доменах приложений с другими уровнями доверия.

  > [!NOTE]
  > Ограниченная возможность пропускать проверки видимости — это функциональная возможность анонимно размещенных динамических методов. Если обычные динамические методы пропускают проверки видимости, выполняемые JIT-компилятором, им следует предоставить полное доверие.

<a name="Example"></a>

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере кода демонстрируется использование флага <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> для разрешения пропуска проверок видимости, выполняемых JIT-компилятором, анонимно размещенными динамическими методами, но только в тех случаях, когда уровень доверия целевого члена не превышает уровень доверия сборки, порождающей код.

В примере определяется класс `Worker`, который может маршалироваться через границы домена приложения. Этот класс содержит две перегрузки метода `AccessPrivateMethod`, которые порождают и выполняют динамические методы. Первая перегрузка порождает динамический метод, который вызывает закрытый метод `PrivateMethod` класса `Worker`. Она может порождать динамический метод с проверкой видимости с помощью JIT-компилятора или без нее. Вторая перегрузка порождает динамический метод, который получает доступ к свойству `internal` (свойство `Friend` в Visual Basic) класса <xref:System.String>.

В примере используется вспомогательный метод для создания набора правил, ограниченного разрешениями `Internet`, а затем создается домен приложения с помощью перегрузки метода <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> для указания необходимости использовать этот набор правил для всего кода, выполняемого в домене. В примере создается экземпляр класса `Worker` в домене приложения, а затем дважды выполняется метод `AccessPrivateMethod`.

- При первом выполнении метода `AccessPrivateMethod` принудительно выполняются проверки видимости с помощью JIT-компилятора. Динамический метод завершается сбоем после вызова, так как проверки видимости с помощью JIT-компилятора не дают ему получить доступ к закрытому методу.

- При втором выполнении метода `AccessPrivateMethod` проверки видимости с помощью JIT-компилятора пропускаются. Компиляция динамического метода завершается сбоем, так как набор правил `Internet` не предоставляет достаточных разрешений для пропуска проверок видимости.

В примере в набор правил добавляется <xref:System.Security.Permissions.ReflectionPermission> с <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>. Затем в примере создается второй домен и указывается, что весь код, выполняемый в домене, получает разрешения из нового набора правил. В примере создается экземпляр класса `Worker` в новом домене приложения, а затем выполняются обе перегрузки метода `AccessPrivateMethod`.

- Выполняется первая перегрузка метода `AccessPrivateMethod`, и проверки видимости с помощью JIT-компилятора пропускаются. Динамический метод успешно компилируется и выполняется, так как сборка, породившая код, является такой же, как сборка, содержащая закрытый метод. Поэтому уровни доверия одинаковы. Если приложение, содержащее класс `Worker`, содержало бы несколько сборок, этот же процесс прошел бы успешно для любой из них, так как они все имели бы один и тот же уровень доверия.

- Выполняется вторая перегрузка метода `AccessPrivateMethod`, и проверки видимости с помощью JIT-компилятора снова пропускаются. На этот раз компиляция динамического метода завершается сбоем, потому что происходит попытка получить доступ к свойству `internal` `FirstChar` класса <xref:System.String>. Сборка, содержащая класс <xref:System.String>, имеет полное доверие. Поэтому уровень доверия выше, чем у сборки, порождающей код.

В этом сравнении показано, как <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> позволяет пропускать в частично доверенном коде проверки видимости, предназначенные для другого частично доверенного кода, без нарушения безопасности доверенного кода.

### <a name="code"></a>Код

[!code-csharp[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#1)]
[!code-vb[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#1)]

## <a name="compiling-the-code"></a>Компиляция кода

- При сборке этого примера кода в Visual Studio необходимо изменить имя класса при передаче его в метод <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>, включив в него пространство имен. По умолчанию пространство имен носит имя проекта. Например, если проект называется PartialTrust, имя класса должно быть PartialTrust.Worker.

## <a name="see-also"></a>См. также

- [Вопросы безопасности в порождении отражения](security-issues-in-reflection-emit.md)
- [Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)

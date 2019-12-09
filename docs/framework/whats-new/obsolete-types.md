---
title: Устаревшие типы в платформе .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, obsolete types
- types, obsolete in .NET Framework 4.5
- obsolete types [.NET Framework]
ms.assetid: e636d024-0fac-45eb-b721-25a8c0ceca8f
ms.openlocfilehash: b7932a553f39e1f1da2a3946878d6224099da8da
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802691"
---
# <a name="obsolete-types-in-the-net-framework"></a>Устаревшие типы в платформе .NET Framework

<a name="introduction"></a> В таблицах этой статьи перечислены устаревшие в .NET Framework 4.5 и .NET Framework 4.6 типы, упорядоченные по сборкам. Используйте следующие ссылки для просмотра списка устаревших типов и рекомендованных альтернатив в каждой сборке. Поскольку эти типы считаются устаревшими, все их члены также являются устаревшими. Список дополнительных устаревших членов в библиотеке классов платформы .NET Framework см. в разделе [Устаревшие члены](obsolete-members.md).

- [Устаревшие типы в системных сборках](#obsolete_types_in_system_assemblies)

  - [mscorlib.dll](#mscorlib)

  - [System.Core.dll](#Core)

  - [System.Data.dll](#data)

  - [System.Data.OracleClient.dll](#oracleclient)

  - [System.Design.dll](#design)

  - [System.dll](#system)

  - [System.EnterpriseServices.dll](#enterpriseservices)

  - [System.Net.dll](#net)

  - [System.ServiceModel.dll](#servicemodel)

  - [System.Web.dll](#web)

  - [System.Web.Mobile.dll](#mobile)

  - [System.Workflow.Activities.dll](#workflow_activities)

  - [System.Workflow.ComponentModel.dll](#workflow_componentmodel)

  - [System.Workflow.Runtime.dll](#workflow_runtime)

  - [System.WorkflowServices.dll](#workflowservices)

  - [System.Xaml.dll](#xaml)

  - [System.Xml.dll](#xml)

  - [WindowsBase.dll](#WindowsBase)

- [Устаревшие типы в сборках Microsoft](#obsolete_types_in_microsoft_assemblies)

  - [IEHost.dll и IEExec.exe](#IEHost)

  - [Microsoft.Build.Engine.dll](#Engine)

  - [Microsoft.JScript.dll](#jscript)

  - [Microsoft.VisualBasic.Compatibility.dll](#VBCompat)

  - [Microsoft.VisualBasic.Compatibility.Data.dll](#VBCompatData)

  - [Microsoft.VisualC.dll](#visualc)

<a name="obsolete_types_in_system_assemblies"></a>

## <a name="obsolete-types-in-system-assemblies"></a>Устаревшие типы в системных сборках

В следующих разделах перечислены типы, объявленные устаревшими в системных сборках. Такие сборки используются при разработке неспециализированных\- приложений, основанных на платформе .NET Framework.

<a name="mscorlib"></a>

### <a name="assembly-mscorlibdll"></a>Сборка: mscorlib.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.ExecutionEngineException?displayProperty=nameWithType>|Этот тип ранее обозначал неопределенную неустранимую ошибку в среде выполнения. Среда выполнения больше не вызывает такого исключения, поэтому этот тип устарел.|
|<xref:System.Collections.CaseInsensitiveHashCodeProvider?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.StringComparer?displayProperty=nameWithType>.|
|<xref:System.Collections.IHashCodeProvider?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Collections.IEqualityComparer?displayProperty=nameWithType>.|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|Класс <xref:System.Configuration.Assemblies.AssemblyHash> не рекомендуется к использованию.|
|<xref:System.Diagnostics.Contracts.Internal.ContractHelper?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5. Вместо этого используйте класс <xref:System.Runtime.CompilerServices.ContractHelper?displayProperty=nameWithType> в пространстве имен System.Runtime.CompilerServices.|
|<xref:System.Reflection.Emit.UnmanagedMarshal?displayProperty=nameWithType>|Доступен альтернативный API. Взамен следует выдавать настраиваемый атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.BIND_OPTS?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.BIND_OPTS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.BINDPTR?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.BINDPTR?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.CALLCONV?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.CALLCONV?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.CONNECTDATA?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.CONNECTDATA?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.DESCKIND?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.DESCKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.DISPPARAMS?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.DISPPARAMS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.ELEMDESC?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.ELEMDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.EXCEPINFO?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.EXCEPINFO?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FILETIME?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.FILETIME?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FUNCDESC?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.FUNCDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FUNCFLAGS?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.FUNCFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FUNCKIND?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.FUNCKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=nameWithType>|Этот атрибут не рекомендуется к использованию и будет удален в будущей версии.|
|<xref:System.Runtime.InteropServices.IDispatchImplType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=nameWithType> не рекомендуется к использованию.|
|<xref:System.Runtime.InteropServices.IDLDESC?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IDLDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.IDLFLAG?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IDLFLAG?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.IMPLTYPEFLAGS?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IMPLTYPEFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.INVOKEKIND?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.INVOKEKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.LIBFLAGS?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.LIBFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.PARAMDESC?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.PARAMDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.PARAMFLAG?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.PARAMFLAG?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.SetWin32ContextInIDispatchAttribute?displayProperty=nameWithType>|Этот атрибут является устаревшим. Домены приложений теперь не учитывают ограничений контекста активации в вызовах IDispatch.|
|<xref:System.Runtime.InteropServices.STATSTG?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.STATSTG?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.SYSKIND?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.SYSKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEATTR?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.TYPEATTR?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEDESC?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.TYPEDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEFLAGS?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.TYPEFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEKIND?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.TYPEKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPELIBATTR?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.TYPELIBATTR?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIBindCtx?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IBindCtx?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIConnectionPoint?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIConnectionPointContainer?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumConnectionPoints?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IEnumConnectionPoints?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumConnections?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IEnumConnections?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumMoniker?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IEnumMoniker?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumString?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IEnumString?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumVARIANT?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIMoniker?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IMoniker?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIPersistFile?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IPersistFile?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIRunningObjectTable?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IRunningObjectTable?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIStream?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMITypeComp?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.ITypeComp?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMITypeInfo?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMITypeLib?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.ITypeLib?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.VARDESC?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.VARDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.VARFLAGS?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.ComTypes.VARFLAGS?displayProperty=nameWithType> .|
|<xref:System.Security.SecurityCriticalScope?displayProperty=nameWithType>|<xref:System.Security.SecurityCriticalScope> применяется только для обеспечения прозрачной совместимости с .NET 2.0.|
|<xref:System.Security.SecurityTreatAsSafeAttribute?displayProperty=nameWithType>|<xref:System.Security.SecurityTreatAsSafeAttribute> применяется только для обеспечения прозрачной совместимости с .NET 2.0. Взамен рекомендуется использовать <xref:System.Security.SecuritySafeCriticalAttribute?displayProperty=nameWithType>.|
|<xref:System.Security.Policy.FirstMatchCodeGroup?displayProperty=nameWithType>|Этот тип устарел и будет удален в одном из будущих выпусков платформы .NET Framework.|
|<xref:System.Security.Policy.PermissionRequestEvidence?displayProperty=nameWithType>|Декларативная безопасность на уровне сборки устарела и больше не обеспечивается средой CLR по умолчанию.|
|<xref:System.Security.Policy.UnionCodeGroup?displayProperty=nameWithType>|Этот тип устарел и будет удален в одном из будущих выпусков платформы .NET Framework.|

[К началу](#introduction)

<a name="Core"></a>

### <a name="assembly-systemcoredll"></a>Сборка: System.Core.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Runtime.CompilerServices.ExecutionScope?displayProperty=nameWithType>|Использование данного типа создает ошибку компилятора.<br /><br /> Этот тип использовать не следует.|

[К началу](#introduction)

<a name="data"></a>

### <a name="assembly-systemdatadll"></a>Сборка: System.Data.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Data.DataSysDescriptionAttribute?displayProperty=nameWithType>|<xref:System.Data.DataSysDescriptionAttribute> не рекомендуется к использованию.|
|<xref:System.Data.PropertyAttributes?displayProperty=nameWithType>|<xref:System.Data.PropertyAttributes> не рекомендуется к использованию.|
|<xref:System.Data.TypedDataSetGenerator?displayProperty=nameWithType>|Класс <xref:System.Data.TypedDataSetGenerator> будет удален в будущем выпуске. В System.Design.dll рекомендуется использовать <xref:System.Data.Design.TypedDataSetGenerator?displayProperty=nameWithType>.|
|<xref:System.Xml.XmlDataDocument?displayProperty=nameWithType>|Класс <xref:System.Xml.XmlDataDocument> будет удален в будущем выпуске.|

[К началу](#introduction)

<a name="oracleclient"></a>

### <a name="assembly-systemdataoracleclientdll"></a>Сборка: System.Data.OracleClient.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Data.OracleClient.OracleClientFactory?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleClientFactory> не рекомендуется к использованию.|
|<xref:System.Data.OracleClient.OracleCommand?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleCommand> не рекомендуется к использованию.|
|<xref:System.Data.OracleClient.OracleCommandBuilder?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleCommandBuilder> не рекомендуется к использованию.|
|<xref:System.Data.OracleClient.OracleConnection?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleConnection> не рекомендуется к использованию.|
|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder> не рекомендуется к использованию.|
|<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleDataAdapter> не рекомендуется к использованию.|
|<xref:System.Data.OracleClient.OraclePermission?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OraclePermission> не рекомендуется к использованию.|
|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=nameWithType> не рекомендуется к использованию.|

[К началу](#introduction)

<a name="design"></a>

### <a name="assembly-systemdesigndll"></a>Сборка: System.Design.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.ComponentModel.Design.LocalizationExtenderProvider?displayProperty=nameWithType>|Этот класс не рекомендуется к использованию. Взамен рекомендуется использовать <xref:System.ComponentModel.Design.Serialization.CodeDomLocalizationProvider?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.DataBindingCollectionConverter?displayProperty=nameWithType>|Этот тип использовать не рекомендуется, поскольку редактирование привязок данных осуществляется не по таблице свойств, а посредством запуска <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.DataBindingCollectionEditor?displayProperty=nameWithType>|Этот тип использовать не рекомендуется, поскольку редактирование привязок данных осуществляется не по таблице свойств, а посредством запуска <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IControlDesignerBehavior?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=nameWithType> и <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IHtmlControlDesignerBehavior?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=nameWithType> и <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ITemplateEditingFrame?displayProperty=nameWithType>|Этот тип использовать не рекомендуется, поскольку редактирование шаблона обрабатывается в <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Чтобы обеспечить редактирование шаблона, данные шаблона следует открыть в свойстве <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType>, а затем вызвать <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IWebFormReferenceManager?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Web.UI.Design.WebFormsReferenceManager?displayProperty=nameWithType>. <xref:System.Web.UI.Design.WebFormsReferenceManager> содержит дополнительные функции и предоставляет более широкие возможности. Доступ к <xref:System.Web.UI.Design.WebFormsReferenceManager> можно получить, используя свойство `RootDesigner.ReferenceManager` в <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IWebFormsDocumentService?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Web.UI.Design.WebFormsRootDesigner?displayProperty=nameWithType>. <xref:System.Web.UI.Design.WebFormsRootDesigner> содержит дополнительные функции и предоставляет более широкие возможности. Доступ к <xref:System.Web.UI.Design.WebFormsRootDesigner> можно получить, используя свойство <xref:System.Web.UI.Design.ControlDesigner.RootDesigner%2A> в <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ITemplateEditingService?displayProperty=nameWithType>|Этот тип использовать не рекомендуется, поскольку редактирование шаблона обрабатывается в <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Чтобы обеспечить редактирование шаблона, данные шаблона следует открыть в свойстве <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType>, а затем вызвать <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ReadWriteControlDesigner?displayProperty=nameWithType>|Взамен рекомендуется прибегнуть к <xref:System.Web.UI.Design.ContainerControlDesigner?displayProperty=nameWithType>, поскольку для редактирования содержимого будет использоваться <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=nameWithType>. Области конструктора упрощают редактирование содержимого.|
|<xref:System.Web.UI.Design.TemplateEditingService?displayProperty=nameWithType>|Этот тип использовать не рекомендуется, поскольку редактирование шаблона обрабатывается в <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Чтобы обеспечить редактирование шаблона, данные шаблона следует открыть в свойстве <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType>, а затем вызвать <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.TemplateEditingVerb?displayProperty=nameWithType>|Этот тип использовать не рекомендуется, поскольку редактирование шаблона обрабатывается в <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Чтобы обеспечить редактирование шаблона, данные шаблона следует открыть в свойстве <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType>, а затем вызвать <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.WebControls.CalendarAutoFormatDialog?displayProperty=nameWithType>|Этот тип использовать не рекомендуется, поскольку диалоговое окно автоформата запускается узлом конструктора. Список доступных автоформатов предоставляется посредством <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> в свойстве <xref:System.Web.UI.Design.ControlDesigner.AutoFormats%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.WebControls.PanelDesigner?displayProperty=nameWithType>|Взамен рекомендуется прибегнуть к <xref:System.Web.UI.Design.WebControls.PanelContainerDesigner?displayProperty=nameWithType>, поскольку для редактирования содержимого будет использоваться <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=nameWithType>. Области конструктора упрощают редактирование содержимого.|

[К началу](#introduction)

<a name="system"></a>

### <a name="assembly-systemdll"></a>Сборка: System.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.ComponentModel.IComNativeDescriptorHandler?displayProperty=nameWithType>|Этот интерфейс не рекомендуется к использованию. Вместо него следует добавить поставщик <xref:System.ComponentModel.TypeDescriptionProvider?displayProperty=nameWithType> для обработки типа <xref:System.ComponentModel.TypeDescriptor.ComObjectType%2A?displayProperty=nameWithType>.|
|<xref:System.ComponentModel.RecommendedAsConfigurableAttribute?displayProperty=nameWithType>|Взамен для работы с новой моделью параметров рекомендуется использовать <xref:System.ComponentModel.SettingsBindableAttribute?displayProperty=nameWithType>.|
|<xref:System.ComponentModel.Design.Serialization.RootDesignerSerializerAttribute?displayProperty=nameWithType>|Этот атрибут является устаревшим. Взамен рекомендуется использовать <xref:System.ComponentModel.Design.Serialization.DesignerSerializerAttribute?displayProperty=nameWithType>.|
|<xref:System.Diagnostics.DiagnosticsConfigurationHandler?displayProperty=nameWithType>|Этот класс не рекомендуется к использованию.|
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=nameWithType>|Этот класс не рекомендуется к использованию. Вместо этого посредством класса <xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType> можно использовать счетчики производительности.|
|<xref:System.Net.GlobalProxySelection?displayProperty=nameWithType>|Этот класс не рекомендуется к использованию. Взамен для получения доступа и задания глобального прокси-сервера по умолчанию следует использовать <xref:System.Net.WebRequest.DefaultWebProxy%2A?displayProperty=nameWithType>. Вместо <xref:System.Net.GlobalProxySelection.GetEmptyWebProxy%2A?displayProperty=nameWithType> следует использовать null.|
|<xref:System.Net.Sockets.SocketClientAccessPolicyProtocol?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|

[К началу](#introduction)

<a name="enterpriseservices"></a>

### <a name="assembly-systementerpriseservicesdll"></a>Сборка: System.EnterpriseServices.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.EnterpriseServices.RegistrationHelperTx?displayProperty=nameWithType>|Класс <xref:System.EnterpriseServices.RegistrationHelperTx> не рекомендуется к использованию.|

[К началу](#introduction)

<a name="net"></a>

### <a name="assembly-systemnetdll"></a>Сборка: System.Net.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Net.INetworkProgress?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Net.IUnsafeWebRequestCreate?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Net.NetworkProgressChangedEventArgs?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Net.UiSynchronizationContext?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Net.Sockets.HttpPolicyDownloaderProtocol?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Net.Sockets.SecurityCriticalAction?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Net.Sockets.SocketPolicy?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Net.Sockets.UdpAnySourceMulticastClient?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Net.Sockets.UdpSingleSourceMulticastClient?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|

[К началу](#introduction)

<a name="servicemodel"></a>

### <a name="assembly-systemservicemodeldll"></a>Сборка: System.ServiceModel.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.ServiceModel.NetPeerTcpBinding?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Функция одноранговых каналов является устаревшей и будет удалена в будущем.|
|<xref:System.ServiceModel.Channels.HttpCookieContainerBindingElement?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Этот тип устарел. Чтобы включить HTTP <xref:System.Net.CookieContainer>, используйте свойство `AllowCookies` привязки HTTP или <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.|
|<xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Функция одноранговых каналов является устаревшей и будет удалена в будущем.|
|<xref:System.ServiceModel.Channels.PeerTransportBindingElement?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Функция одноранговых каналов является устаревшей и будет удалена в будущем.|
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingCollectionElement?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Функция одноранговых каналов является устаревшей и будет удалена в будущем.|
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Функция одноранговых каналов является устаревшей и будет удалена в будущем.|
|<xref:System.ServiceModel.Configuration.PeerTransportElement?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Функция одноранговых каналов является устаревшей и будет удалена в будущем.|
|<xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Функция одноранговых каналов является устаревшей и будет удалена в будущем.|

[К началу](#introduction)

<a name="web"></a>

### <a name="assembly-systemwebdll"></a>Сборка: System.Web.dll.

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Web.Configuration.PassportAuthentication?displayProperty=nameWithType>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](https://account.microsoft.com/account/Account?destrt=home-index), и в дальнейшем необходимости в ней нет.|
|<xref:System.Web.Mail.MailAttachment?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Net.Mail.Attachment?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailEncoding?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Net.Mime.TransferEncoding?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailFormat?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Net.Mail.MailMessage.IsBodyHtml%2A?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Net.Mail.MailMessage?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailPriority?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Net.Mail.MailPriority?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.SmtpMail?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>.|
|<xref:System.Web.Security.PassportAuthenticationEventArgs?displayProperty=nameWithType>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](https://account.microsoft.com/account/Account?destrt=home-index), и в дальнейшем необходимости в ней нет.|
|<xref:System.Web.Security.PassportAuthenticationEventHandler?displayProperty=nameWithType>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](https://account.microsoft.com/account/Account?destrt=home-index), и в дальнейшем необходимости в ней нет.|
|<xref:System.Web.Security.PassportAuthenticationModule?displayProperty=nameWithType>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](https://account.microsoft.com/account/Account?destrt=home-index), и в дальнейшем необходимости в ней нет.|
|<xref:System.Web.Security.PassportIdentity?displayProperty=nameWithType>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](https://account.microsoft.com/account/Account?destrt=home-index), и в дальнейшем необходимости в ней нет.|
|<xref:System.Web.Security.PassportPrincipal?displayProperty=nameWithType>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](https://account.microsoft.com/account/Account?destrt=home-index), и в дальнейшем необходимости в ней нет.|
|<xref:System.Web.UI.ObjectConverter?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Convert?displayProperty=nameWithType> и <xref:System.String.Format%2A?displayProperty=nameWithType>.|

[К началу](#introduction)

<a name="mobile"></a>

### <a name="assembly-systemwebmobiledll"></a>Сборка: System.Web.Mobile.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Web.Mobile.CookielessData?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFilterElement?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFilterElementCollection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFiltersSection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.ErrorHandlerModule?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileCapabilities?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileDeviceCapabilitiesSectionHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileErrorInfo?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileFormsAuthentication?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.IMobileDesigner?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.IMobileWebFormServices?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.MobileResource?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.Converters.DataFieldConverter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.Converters.DataMemberConverter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.AdRotator?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Alignment?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ArrayListCollectionBase?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.BaseValidator?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.BooleanOption?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Calendar?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Command?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CommandFormat?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CompareValidator?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Constants?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlElement?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlElementCollection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlPager?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CustomValidator?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DesignerAdapterAttribute?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceElement?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceElementCollection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceOverridableAttribute?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecific?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoice?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceCollection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateContainer?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ErrorFormatterPage?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FontInfo?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FontSize?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Form?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FormControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FormMethod?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IControlAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Image?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IObjectListFieldCollection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IPageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ItemPager?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ITemplateable?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Label?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Link?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.List?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListCommandEventArgs?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListCommandEventHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDataBindEventArgs?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDataBindEventHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDecoration?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListSelectType?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralLink?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralText?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralTextContainerControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralTextControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LoadItemsEventArgs?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LoadItemsEventHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControl?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlsSection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlsSectionHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItem?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItemCollection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItemType?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobilePage?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileTypeNameConverter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileUserControl?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectList?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommand?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandCollection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventArgs?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventArgs?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListField?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListFieldCollection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListItem?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListItemCollection?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventArgs?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventArgs?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListTitleAttribute?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListViewMode?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PagedControl?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PagerStyle?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Panel?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PanelControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PersistNameAttribute?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PhoneCall?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RangeValidator?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RegularExpressionValidator?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RequiredFieldValidator?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.SelectionList?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Style?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.StyleSheet?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.StyleSheetControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TemplateContainer?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextBox?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextBoxControlBuilder?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextControl?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextView?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextViewElement?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ValidationSummary?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Wrapping?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCalendarAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCommandAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlFormAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlImageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlLinkAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlMobileTextWriter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPhoneCallAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlSelectionListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlTextBoxAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ControlAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCalendarAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCommandAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlControlAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlFormAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlImageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLabelAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLinkAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLiteralTextAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlMobileTextWriter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlObjectListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPanelAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPhoneCallAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlSelectionListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextBoxAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextViewAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidationSummaryAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidatorAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.MobileTextWriter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.MultiPartWriter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlMobileTextWriter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlPageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlCalendarAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlCommandAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlControlAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlFormAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlImageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLabelAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLinkAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLiteralTextAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlMobileTextWriter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlObjectListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPanelAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPhoneCallAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPostFieldType?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlSelectionListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextBoxAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextViewAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidationSummaryAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidatorAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.Doctype?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.StyleSheetLocation?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCalendarAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCommandAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlControlAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCssHandler?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlFormAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlImageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLabelAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLinkAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLiteralTextAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlMobileTextWriter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlObjectListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPageAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPanelAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPhoneCallAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlSelectionListAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextBoxAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextViewAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidationSummaryAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidatorAdapter?displayProperty=nameWithType>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](/aspnet/mobile/overview).|

[К началу](#introduction)

<a name="workflow_activities"></a>

### <a name="assembly-systemworkflowactivitiesdll"></a>Сборка: System.Workflow.Activities.dll

|Тип|Сообщение|
|----------|-------------|
|Все типы в пространстве имен <xref:System.Workflow.Activities?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Configuration.ActiveDirectoryRoleFactoryConfiguration?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleActionTrackingEvent?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleConditionReference?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleSetReference?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|

[К началу](#introduction)

<a name="workflow_componentmodel"></a>

### <a name="assembly-systemworkflowcomponentmodeldll"></a>Сборка: System.Workflow.ComponentModel.dll

|Тип|Сообщение|
|----------|-------------|
|Все типы в пространстве имен <xref:System.Workflow.ComponentModel>, кроме <xref:System.Workflow.ComponentModel.GetValueOverride?displayProperty=nameWithType> и <xref:System.Workflow.ComponentModel.SetValueOverride?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|Все типы в пространстве имен <xref:System.Workflow.ComponentModel.Compiler>, кроме <xref:System.Workflow.ComponentModel.Compiler.ValidationError?displayProperty=nameWithType> и <xref:System.Workflow.ComponentModel.Compiler.ValidationErrorCollection?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|Все типы в пространстве имен <xref:System.Workflow.ComponentModel.Design>, кроме <xref:System.Workflow.ComponentModel.Design.ConnectorEventHandler>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializationManager?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializer?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityMarkupSerializer?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivitySurrogateSelector?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityTypeCodeDomSerializer?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.CompositeActivityMarkupSerializer?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.DependencyObjectCodeDomSerializer?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|

[К началу](#introduction)

<a name="workflow_runtime"></a>

### <a name="assembly-systemworkflowruntimedll"></a>Сборка: System.Workflow.Runtime.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Activities.Statements.Interop?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br />Типы Workflow Foundation 3.0 являются устаревшими. Вместо них используйте типы Workflow 4.0 из <xref:System.Activities>\*.|
|<xref:System.Activities.Tracking.InteropTrackingRecord?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br />Типы Workflow Foundation 3.0 являются устаревшими. Вместо них используйте типы Workflow 4.0 из <xref:System.Activities>\*.|
|Все типы в пространстве имен <xref:System.Workflow.Runtime>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|Все типы в пространстве имен <xref:System.Workflow.Runtime.Configuration>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|Все типы в пространстве имен <xref:System.Workflow.Runtime.DebugEngine>, кроме <xref:System.Workflow.Runtime.DebugEngine.DebugEngineCallback>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|Все типы в пространстве имен <xref:System.Workflow.Runtime.Hosting>, кроме <xref:System.Workflow.Runtime.Hosting.WorkflowCommitWorkBatchService.CommitWorkBatchCallback>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|
|Все типы в пространстве имен <xref:System.Workflow.Runtime.Tracking>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* не рекомендуются. Вместо этого используйте новые типы из <xref:System.Activities>\*.|

[К началу](#introduction)

<a name="workflowservices"></a>

### <a name="assembly-systemworkflowservicesdll"></a>Сборка: System.WorkflowServices.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.ServiceModel.WorkflowServiceHost?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Activation.WorkflowServiceHostFactory?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Activities.Description.WorkflowRuntimeEndpoint?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.ExtendedWorkflowRuntimeServiceElementCollection?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.PersistenceProviderElement?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.WorkflowRuntimeElement?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.DurableOperationAttribute?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.DurableServiceAttribute?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.PersistenceProviderBehavior?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.UnknownExceptionAction?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.WorkflowRuntimeBehavior?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Dispatcher.DurableOperationContext?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.InstanceLockException?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.InstanceNotFoundException?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.LockingPersistenceProvider?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceException?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceProvider?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceProviderFactory?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.SqlPersistenceProviderFactory?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|Все типы в пространстве имен <xref:System.Workflow.Activities?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|
|<xref:System.Workflow.Runtime.Hosting.ChannelManagerService?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо этого используйте новые типы WF 4 из <xref:System.Activities>\*.|

[К началу](#introduction)

<a name="xaml"></a>

### <a name="assembly-systemxamldll"></a>Сборка: System.Xaml.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute?displayProperty=nameWithType>|Не используется синтаксическим анализатором XAML. Дополнительные сведения см. в <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=nameWithType>.|

[К началу](#introduction)

<a name="xml"></a>

### <a name="assembly-systemxmldll"></a>Сборка: System.Xml.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Xml.IApplicationResourceStreamResolver?displayProperty=nameWithType>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Xml.Schema.XmlSchemaCollection?displayProperty=nameWithType>|<xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> рекомендуется использовать для компиляции и проверки схемы.|
|<xref:System.Xml.XmlValidatingReader?displayProperty=nameWithType>|Взамен рекомендуется использовать <xref:System.Xml.XmlReader?displayProperty=nameWithType>, создаваемый методом <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> с соответствующими параметрами <xref:System.Xml.XmlReaderSettings?displayProperty=nameWithType>.|
|<xref:System.Xml.XmlXapResolver?displayProperty=nameWithType>|Использование данного типа создает ошибку компилятора. Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|
|<xref:System.Xml.Xsl.XslTransform?displayProperty=nameWithType>|Этот класс не рекомендуется к использованию. Взамен рекомендуется использовать <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>.|

[К началу](#introduction)

<a name="WindowsBase"></a>

### <a name="assembly-windowsbasedll"></a>Сборка: WindowsBase.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=nameWithType>|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=nameWithType> не рекомендуется к использованию. Этот интерфейс больше не используется.|

[К началу](#introduction)

<a name="obsolete_types_in_microsoft_assemblies"></a>

## <a name="obsolete-types-in-microsoft-assemblies"></a>Устаревшие типы в сборках Microsoft

В следующих разделах перечислены устаревшие типы в системных сборках корпорации Microsoft. Это сборки специального назначения, например, сборки для конкретного языка (как Microsoft.JScript.dll или Microsoft.VisualC.dll).

<a name="IEHost"></a>

### <a name="assembly-iehostdll-and-ieexecexe"></a>Сборка: IEHost.dll and IEExec.exe

Сборки IEHost.dll и IEExec.exe удалены из платформы .NET Framework. Все их типы и члены устарели и не поддерживаются начиная с .NET Framework 4. Эти сборки использовались для размещения элементов управления Windows Forms и для запуска исполняемых файлов в Internet Explorer. Взамен рекомендуется использовать ClickOnce, XAML-приложения браузера (XBAP) и Microsoft Silverlight.

[К началу](#introduction)

<a name="Engine"></a>

### <a name="assembly-microsoftbuildenginedll"></a>Сборка: Microsoft.Build.Engine.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=nameWithType>|Этот класс не рекомендуется к использованию. Вместо него используйте <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=nameWithType> из сборки *Microsoft.Build*.|
|<xref:Microsoft.Build.BuildEngine.Project?displayProperty=nameWithType>|Этот класс не рекомендуется к использованию. Вместо него используйте <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=nameWithType> из сборки *Microsoft.Build*.|

[К началу](#introduction)

<a name="jscript"></a>

### <a name="assembly-microsoftjscriptdll"></a>Сборка: Microsoft.JScript.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:Microsoft.JScript.Vsa.BaseVsaEngine?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.BaseVsaSite?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.BaseVsaStartup?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaCodeItem?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaEngine?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaError?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaGlobalItem?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaItem?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaItems?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaPersistSite?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaReferenceItem?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaSite?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaError?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaException?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaItemFlag?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaItemType?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.ResInfo?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.VsaEngine?displayProperty=nameWithType>|Этот тип был объявлен устаревшим в Visual Studio 2005; тип для замены отсутствует. Дополнительные справочные сведения см. в документации по <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|

[К началу](#introduction)

<a name="VBCompat"></a>

### <a name="assembly-microsoftvisualbasiccompatibilitydll"></a>Сборка: Microsoft.VisualBasic.Compatibility.dll

Сведения о миграции с Visual Basic 6 см. в разделе [Центр ресурсов по Visual Basic 6.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-basic-6/visual-basic-6.0-documentation).

|Тип|Сообщение|
|----------|-------------|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseControlArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseOcxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ButtonArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckedListBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ColorDialogArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ComboBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBox?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBox?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBox?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FixedLengthString?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FontDialogArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FormShowConstants?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.GroupBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.HScrollBarArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ImageListArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LabelArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxItem?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListViewArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LoadResConstants?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MaskedTextBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MenuItemArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MouseButtonConstants?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.OpenFileDialogArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PanelArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PictureBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PrintDialogArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ProgressBarArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RadioButtonArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RichTextBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SaveFileDialogArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ScaleMode?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ShiftConstants?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusBarArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusStripArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.Support?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TabControlArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TextBoxArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TimerArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolBarArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripMenuItemArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TreeViewArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.VScrollBarArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebBrowserArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClass?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassContainingClassNotOptional?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassCouldNotFindEvent?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemCannotBeCurrentWebItem?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemRespondNotFound?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassUserWebClassNameNotOptional?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebClassFileNameNotOptional?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebItemNotValid?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItem?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemAssociatedWebClassNotOptional?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemClosingTagNotFound?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadEmbeddedResource?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadTemplateFile?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNameNotOptional?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNoTemplateSpecified?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemTooManyNestedTags?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemUnexpectedErrorReadingTemplateFile?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ZOrderConstants?displayProperty=nameWithType>|Этот элемент устарел.|

[К началу](#introduction)

<a name="VBCompatData"></a>

### <a name="assembly-microsoftvisualbasiccompatibilitydatadll"></a>Сборка: Microsoft.VisualBasic.Compatibility.Data.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.BOFActionEnum?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EndOfRecordsetDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EOFActionEnum?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.ErrorDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchCompleteDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchProgressDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FieldChangeCompleteDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.MoveCompleteDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.OrientationEnum?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordChangeCompleteDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordsetChangeCompleteDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeFieldDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordsetDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillMoveDelegate?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODCArray?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseDataEnvironment?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BindingCollectionEnumerator?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CONNECTDATA?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBBINDING?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBCOLUMNINFO?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBID?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBinding?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBindingCollection?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBKINDENUM?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBPROPIDSET?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IAccessor?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IChapteredRowset?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IColumnsInfo?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPoint?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPointContainer?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormat?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormatDisp?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnectionPoints?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnections?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPosition?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPositionChange?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowset?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetChange?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetIdentity?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetInfo?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetNotify?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBinding?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBindingCollection?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SRDescriptionAttribute?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UGUID?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UNAME?displayProperty=nameWithType>|Этот элемент устарел.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UpdateMode?displayProperty=nameWithType>|Этот элемент устарел.|

[К началу](#introduction)

<a name="visualc"></a>

### <a name="assembly-microsoftvisualcdll"></a>Сборка: Microsoft.VisualC.dll

|Тип|Сообщение|
|----------|-------------|
|<xref:Microsoft.VisualC.DebugInfoInPDBAttribute?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|
|<xref:Microsoft.VisualC.DecoratedNameAttribute?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|
|<xref:Microsoft.VisualC.IsConstModifier?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|
|<xref:Microsoft.VisualC.IsCXXReferenceModifier?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|
|<xref:Microsoft.VisualC.IsLongModifier?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|
|<xref:Microsoft.VisualC.IsSignedModifier?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|
|<xref:Microsoft.VisualC.IsVolatileModifier?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|
|<xref:Microsoft.VisualC.MiscellaneousBitsAttribute?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|
|<xref:Microsoft.VisualC.NeedsCopyConstructorModifier?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|
|<xref:Microsoft.VisualC.NoSignSpecifiedModifier?displayProperty=nameWithType>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|

## <a name="see-also"></a>См. также

- [Устаревшие классы библиотеки классов](whats-obsolete.md)
- [Устаревшие члены](obsolete-members.md)

---
title: "Устаревшие типы в платформе .NET Framework | Документы Майкрософт"
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
- .NET Framework 4.5, obsolete types
- types, obsolete in .NET Framework 4.5
- obsolete types [.NET Framework]
ms.assetid: e636d024-0fac-45eb-b721-25a8c0ceca8f
caps.latest.revision: 41
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 175e46e3729190423b85296d7c7c47b136339305
ms.contentlocale: ru-ru
ms.lasthandoff: 04/18/2017

---
# <a name="obsolete-types-in-the-net-framework"></a>Устаревшие типы в платформе .NET Framework
<a name="introduction"></a>В таблицах этой статьи перечислены типы, которые являются устаревшими в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] и [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Они сгруппированы по сборкам. Используйте следующие ссылки для просмотра списка устаревших типов и рекомендованных альтернатив в каждой сборке. Поскольку эти типы считаются устаревшими, все их члены также являются устаревшими. Список дополнительных устаревших членов в библиотеке классов платформы .NET Framework см. в разделе [Устаревшие члены](../../../docs/framework/whats-new/obsolete-members.md).  
  
-   [Устаревшие типы в системных сборках](#obsolete_types_in_system_assemblies)  
  
    -   [mscorlib.dll](#mscorlib)  
  
    -   [System.Core.dll](#Core)  
  
    -   [System.Data.dll](#data)  
  
    -   [System.Data.OracleClient.dll](#oracleclient)  
  
    -   [System.Design.dll](#design)  
  
    -   [System.dll](#system)  
  
    -   [System.EnterpriseServices.dll](#enterpriseservices)  
  
    -   [System.Net.dll](#net)  
  
    -   [System.ServiceModel.dll](#servicemodel)  
  
    -   [System.Web.dll](#web)  
  
    -   [System.Web.Mobile.dll](#mobile)  
  
    -   [System.Workflow.Activities.dll](#workflow_activities)  
  
    -   [System.Workflow.ComponentModel.dll](#workflow_componentmodel)  
  
    -   [System.Workflow.Runtime.dll](#workflow_runtime)  
  
    -   [System.WorkflowServices.dll](#workflowservices)  
  
    -   [System.Xaml.dll](#xaml)  
  
    -   [System.Xml.dll](#xml)  
  
    -   [WindowsBase.dll](#WindowsBase)  
  
-   [Устаревшие типы в сборках Microsoft](#obsolete_types_in_microsoft_assemblies)  
  
    -   [IEHost.dll и IEExec.exe](#IEHost)  
  
    -   [Microsoft.Build.Engine.dll](#Engine)  
  
    -   [Microsoft.JScript.dll](#jscript)  
  
    -   [Microsoft.VisualBasic.Compatibility.dll](#VBCompat)  
  
    -   [Microsoft.VisualBasic.Compatibility.Data.dll](#VBCompatData)  
  
    -   [Microsoft.VisualC.dll](#visualc)  
  
<a name="obsolete_types_in_system_assemblies"></a>   
## <a name="obsolete-types-in-system-assemblies"></a>Устаревшие типы в системных сборках  
 В следующих разделах перечислены типы, объявленные устаревшими в системных сборках. Такие сборки используются при разработке неспециализированных\- приложений, основанных на платформе .NET Framework.  
  
<a name="mscorlib"></a>   
### <a name="assembly-mscorlibdll"></a>Сборка: mscorlib.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.ExecutionEngineException?displayProperty=fullName>|Этот тип ранее обозначал неопределенную неустранимую ошибку в среде выполнения. Среда выполнения больше не вызывает такого исключения, поэтому этот тип устарел.|  
|<xref:System.Collections.CaseInsensitiveHashCodeProvider?displayProperty=fullName>|Используйте вместо него <xref:System.StringComparer?displayProperty=fullName>.|  
|<xref:System.Collections.IHashCodeProvider?displayProperty=fullName>|Используйте вместо него <xref:System.Collections.IEqualityComparer?displayProperty=fullName>.|  
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=fullName>|Класс <xref:System.Configuration.Assemblies.AssemblyHash> является устаревшим.|  
|<xref:System.Diagnostics.Contracts.Internal.ContractHelper?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5. Используйте вместо него класс <xref:System.Runtime.CompilerServices.ContractHelper?displayProperty=fullName> в пространстве имен System.Runtime.CompilerServices.|  
|<xref:System.Reflection.Emit.UnmanagedMarshal?displayProperty=fullName>|Доступен альтернативный API. Используйте пользовательский атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.BIND_OPTS?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.BIND_OPTS?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.BINDPTR?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.BINDPTR?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.CALLCONV?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.CALLCONV?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.CONNECTDATA?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.CONNECTDATA?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.DESCKIND?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.DESCKIND?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.DISPPARAMS?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.DISPPARAMS?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.ELEMDESC?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.ELEMDESC?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.EXCEPINFO?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.EXCEPINFO?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.FILETIME?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.FILETIME?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.FUNCDESC?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.FUNCDESC?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.FUNCFLAGS?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.FUNCFLAGS?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.FUNCKIND?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.FUNCKIND?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=fullName>|Этот атрибут не рекомендуется к использованию и будет удален в будущей версии.|  
|<xref:System.Runtime.InteropServices.IDispatchImplType?displayProperty=fullName>|Тип <xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=fullName> является устаревшим.|  
|<xref:System.Runtime.InteropServices.IDLDESC?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IDLDESC?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.IDLFLAG?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IDLFLAG?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.IMPLTYPEFLAGS?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IMPLTYPEFLAGS?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.INVOKEKIND?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.INVOKEKIND?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.LIBFLAGS?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.LIBFLAGS?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.PARAMDESC?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.PARAMDESC?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.PARAMFLAG?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.PARAMFLAG?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.SetWin32ContextInIDispatchAttribute?displayProperty=fullName>|Этот атрибут является устаревшим. Домены приложений теперь не учитывают ограничений контекста активации в вызовах IDispatch.|  
|<xref:System.Runtime.InteropServices.STATSTG?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.STATSTG?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.SYSKIND?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.SYSKIND?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.TYPEATTR?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.TYPEATTR?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.TYPEDESC?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.TYPEDESC?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.TYPEFLAGS?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.TYPEFLAGS?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.TYPEKIND?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.TYPEKIND?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.TYPELIBATTR?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.TYPELIBATTR?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIBindCtx?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IBindCtx?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIConnectionPoint?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIConnectionPointContainer?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumConnectionPoints?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IEnumConnectionPoints?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumConnections?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IEnumConnections?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumMoniker?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IEnumMoniker?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumString?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IEnumString?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumVARIANT?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIMoniker?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IMoniker?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIPersistFile?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IPersistFile?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIRunningObjectTable?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IRunningObjectTable?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMIStream?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMITypeComp?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.ITypeComp?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMITypeInfo?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.UCOMITypeLib?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.ITypeLib?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.VARDESC?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.VARDESC?displayProperty=fullName>.|  
|<xref:System.Runtime.InteropServices.VARFLAGS?displayProperty=fullName>|Используйте вместо него <xref:System.Runtime.InteropServices.ComTypes.VARFLAGS?displayProperty=fullName>.|  
|<xref:System.Security.SecurityCriticalScope?displayProperty=fullName>|Тип <xref:System.Security.SecurityCriticalScope> используется только для обеспечения прозрачной совместимости с .NET 2.0.|  
|<xref:System.Security.SecurityTreatAsSafeAttribute?displayProperty=fullName>|Тип <xref:System.Security.SecurityTreatAsSafeAttribute> используется только для обеспечения прозрачной совместимости с .NET 2.0. Используйте вместо него <xref:System.Security.SecuritySafeCriticalAttribute?displayProperty=fullName>.|  
|<xref:System.Security.Policy.FirstMatchCodeGroup?displayProperty=fullName>|Этот тип устарел и будет удален в одном из будущих выпусков платформы .NET Framework.|  
|<xref:System.Security.Policy.PermissionRequestEvidence?displayProperty=fullName>|Декларативная безопасность на уровне сборки устарела и больше не обеспечивается средой CLR по умолчанию.|  
|<xref:System.Security.Policy.UnionCodeGroup?displayProperty=fullName>|Этот тип устарел и будет удален в одном из будущих выпусков платформы .NET Framework.|  
  
 [К началу](#introduction)  
  
<a name="Core"></a>   
### <a name="assembly-systemcoredll"></a>Сборка: System.Core.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.Runtime.CompilerServices.ExecutionScope?displayProperty=fullName>|Использование данного типа создает ошибку компилятора.<br /><br /> Этот тип использовать не следует.|  
  
 [К началу](#introduction)  
  
<a name="data"></a>   
### <a name="assembly-systemdatadll"></a>Сборка: System.Data.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.Data.DataSysDescriptionAttribute?displayProperty=fullName>|<xref:System.Data.DataSysDescriptionAttribute> является устаревшим.|  
|<xref:System.Data.PropertyAttributes?displayProperty=fullName>|Тип <xref:System.Data.PropertyAttributes> является устаревшим.|  
|<xref:System.Data.TypedDataSetGenerator?displayProperty=fullName>|Класс <xref:System.Data.TypedDataSetGenerator> будет удален в следующем выпуске. Используйте <xref:System.Data.Design.TypedDataSetGenerator?displayProperty=fullName> в библиотеке System.Design.dll.|  
|<xref:System.Xml.XmlDataDocument?displayProperty=fullName>|Класс <xref:System.Xml.XmlDataDocument> будет удален в следующем выпуске.|  
  
 [К началу](#introduction)  
  
<a name="oracleclient"></a>   
### <a name="assembly-systemdataoracleclientdll"></a>Сборка: System.Data.OracleClient.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.Data.OracleClient.OracleClientFactory?displayProperty=fullName>|Тип <xref:System.Data.OracleClient.OracleClientFactory> является устаревшим.|  
|<xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName>|Тип <xref:System.Data.OracleClient.OracleCommand> является устаревшим.|  
|<xref:System.Data.OracleClient.OracleCommandBuilder?displayProperty=fullName>|Тип <xref:System.Data.OracleClient.OracleCommandBuilder> является устаревшим.|  
|<xref:System.Data.OracleClient.OracleConnection?displayProperty=fullName>|Тип <xref:System.Data.OracleClient.OracleConnection> является устаревшим.|  
|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=fullName>|Тип <xref:System.Data.OracleClient.OracleConnectionStringBuilder> является устаревшим.|  
|<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>|Тип <xref:System.Data.OracleClient.OracleDataAdapter> является устаревшим.|  
|<xref:System.Data.OracleClient.OraclePermission?displayProperty=fullName>|Тип <xref:System.Data.OracleClient.OraclePermission> является устаревшим.|  
|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName>|Тип <xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName> является устаревшим.|  
  
 [К началу](#introduction)  
  
<a name="design"></a>   
### <a name="assembly-systemdesigndll"></a>Сборка: System.Design.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.ComponentModel.Design.LocalizationExtenderProvider?displayProperty=fullName>|Этот класс не рекомендуется к использованию. Используйте вместо него <xref:System.ComponentModel.Design.Serialization.CodeDomLocalizationProvider?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.DataBindingCollectionConverter?displayProperty=fullName>|Этот тип использовать не рекомендуется, так как редактирование DataBindings осуществляется через <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=fullName> вместо сетки свойств.|  
|<xref:System.Web.UI.Design.DataBindingCollectionEditor?displayProperty=fullName>|Этот тип использовать не рекомендуется, так как редактирование DataBindings осуществляется через <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=fullName> вместо сетки свойств.|  
|<xref:System.Web.UI.Design.IControlDesignerBehavior?displayProperty=fullName>|Рекомендуется использовать <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=fullName> и <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.IHtmlControlDesignerBehavior?displayProperty=fullName>|Рекомендуется использовать <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=fullName> и <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.ITemplateEditingFrame?displayProperty=fullName>|Не рекомендуется использовать этот тип, так как редактирование шаблона управляется <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>. Чтобы обеспечить редактирование шаблона, объявите данные шаблона с помощью свойства <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> и вызовите <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.IWebFormReferenceManager?displayProperty=fullName>|Рекомендуется использовать <xref:System.Web.UI.Design.WebFormsReferenceManager?displayProperty=fullName>. Тип <xref:System.Web.UI.Design.WebFormsReferenceManager> содержит дополнительные функции и предоставляет более широкие возможности. Для получения <xref:System.Web.UI.Design.WebFormsReferenceManager> используйте свойство `RootDesigner.ReferenceManager` из <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.IWebFormsDocumentService?displayProperty=fullName>|Рекомендуется использовать <xref:System.Web.UI.Design.WebFormsRootDesigner?displayProperty=fullName>. Тип <xref:System.Web.UI.Design.WebFormsRootDesigner> содержит дополнительные функции и предоставляет более широкие возможности. Для получения <xref:System.Web.UI.Design.WebFormsRootDesigner> используйте свойство <xref:System.Web.UI.Design.ControlDesigner.RootDesigner%2A> из <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.ITemplateEditingService?displayProperty=fullName>|Не рекомендуется использовать этот тип, так как редактирование шаблона управляется <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>. Чтобы обеспечить редактирование шаблона, объявите данные шаблона с помощью свойства <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> и вызовите <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.ReadWriteControlDesigner?displayProperty=fullName>|Рекомендуется использовать <xref:System.Web.UI.Design.ContainerControlDesigner?displayProperty=fullName>, так как он использует <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=fullName> для редактирования содержимого. Области конструктора упрощают редактирование содержимого.|  
|<xref:System.Web.UI.Design.TemplateEditingService?displayProperty=fullName>|Не рекомендуется использовать этот тип, так как редактирование шаблона управляется <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>. Чтобы обеспечить редактирование шаблона, объявите данные шаблона с помощью свойства <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> и вызовите <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.TemplateEditingVerb?displayProperty=fullName>|Не рекомендуется использовать этот тип, так как редактирование шаблона управляется <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>. Чтобы обеспечить редактирование шаблона, объявите данные шаблона с помощью свойства <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> и вызовите <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.WebControls.CalendarAutoFormatDialog?displayProperty=fullName>|Этот тип использовать не рекомендуется, поскольку диалоговое окно автоформата запускается узлом конструктора. Список доступных форматов AutoFormats предоставляется на <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> в свойстве <xref:System.Web.UI.Design.ControlDesigner.AutoFormats%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.WebControls.PanelDesigner?displayProperty=fullName>|Рекомендуется использовать <xref:System.Web.UI.Design.WebControls.PanelContainerDesigner?displayProperty=fullName>, так как он использует <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=fullName> для редактирования содержимого. Области конструктора упрощают редактирование содержимого.|  
  
 [К началу](#introduction)  
  
<a name="system"></a>   
### <a name="assembly-systemdll"></a>Сборка: System.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.ComponentModel.IComNativeDescriptorHandler?displayProperty=fullName>|Этот интерфейс не рекомендуется к использованию. Добавьте вместо него <xref:System.ComponentModel.TypeDescriptionProvider?displayProperty=fullName> для управления типом <xref:System.ComponentModel.TypeDescriptor.ComObjectType%2A?displayProperty=fullName>.|  
|<xref:System.ComponentModel.RecommendedAsConfigurableAttribute?displayProperty=fullName>|Используйте вместо него <xref:System.ComponentModel.SettingsBindableAttribute?displayProperty=fullName> для работы с новой моделью параметров.|  
|<xref:System.ComponentModel.Design.Serialization.RootDesignerSerializerAttribute?displayProperty=fullName>|Этот атрибут является устаревшим. Используйте вместо него <xref:System.ComponentModel.Design.Serialization.DesignerSerializerAttribute?displayProperty=fullName>. Например, чтобы задать корневой конструктор для CodeDom следует использовать `DesignerSerializerAttribute\(...,typeof\(TypeCodeDomSerializer\)\)`.|  
|<xref:System.Diagnostics.DiagnosticsConfigurationHandler?displayProperty=fullName>|Этот класс не рекомендуется к использованию.|  
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=fullName>|Этот класс не рекомендуется к использованию. Используйте вместо него счетчики производительности, реализованные с помощью класса <xref:System.Diagnostics.PerformanceCounter?displayProperty=fullName>.|  
|<xref:System.Net.GlobalProxySelection?displayProperty=fullName>|Этот класс не рекомендуется к использованию. Используйте вместо него <xref:System.Net.WebRequest.DefaultWebProxy%2A?displayProperty=fullName> для доступа к глобальному прокси-серверу и его настройки. Используйте вместо него <xref:System.Net.GlobalProxySelection.GetEmptyWebProxy%2A?displayProperty=fullName> значение NULL.|  
|<xref:System.Net.Sockets.SocketClientAccessPolicyProtocol?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
  
 [К началу](#introduction)  
  
<a name="enterpriseservices"></a>   
### <a name="assembly-systementerpriseservicesdll"></a>Сборка: System.EnterpriseServices.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.EnterpriseServices.RegistrationHelperTx?displayProperty=fullName>|Класс <xref:System.EnterpriseServices.RegistrationHelperTx> является устаревшим.|  
  
 [К началу](#introduction)  
  
<a name="net"></a>   
### <a name="assembly-systemnetdll"></a>Сборка: System.Net.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.Net.INetworkProgress?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Net.IUnsafeWebRequestCreate?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Net.NetworkProgressChangedEventArgs?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Net.UiSynchronizationContext?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Net.Sockets.HttpPolicyDownloaderProtocol?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Net.Sockets.SecurityCriticalAction?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Net.Sockets.SocketPolicy?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Net.Sockets.UdpAnySourceMulticastClient?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Net.Sockets.UdpSingleSourceMulticastClient?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
  
 [К началу](#introduction)  
  
<a name="servicemodel"></a>   
### <a name="assembly-systemservicemodeldll"></a>Сборка: System.ServiceModel.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.ServiceModel.NetPeerTcpBinding?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Возможность одноранговых каналов является устаревшей и будет удалена в будущем.|  
|<xref:System.ServiceModel.Channels.HttpCookieContainerBindingElement?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Этот тип устарел. Чтобы включить контейнер <xref:System.Net.CookieContainer> Http, используйте свойство `AllowCookies` в привязке Http или в элементе <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.|  
|<xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Возможность одноранговых каналов является устаревшей и будет удалена в будущем.|  
|<xref:System.ServiceModel.Channels.PeerTransportBindingElement?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Возможность одноранговых каналов является устаревшей и будет удалена в будущем.|  
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingCollectionElement?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Возможность одноранговых каналов является устаревшей и будет удалена в будущем.|  
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Возможность одноранговых каналов является устаревшей и будет удалена в будущем.|  
|<xref:System.ServiceModel.Configuration.PeerTransportElement?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Возможность одноранговых каналов является устаревшей и будет удалена в будущем.|  
|<xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Возможность одноранговых каналов является устаревшей и будет удалена в будущем.|  
  
 [К началу](#introduction)  
  
<a name="web"></a>   
### <a name="assembly-systemwebdll"></a>Сборка: System.Web.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.Web.Configuration.PassportAuthentication?displayProperty=fullName>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](http://go.microsoft.com/fwlink/?LinkId=733413), и в дальнейшем необходимости в ней нет.|  
|<xref:System.Web.Mail.MailAttachment?displayProperty=fullName>|Рекомендуется использовать <xref:System.Net.Mail.Attachment?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailEncoding?displayProperty=fullName>|Рекомендуется использовать <xref:System.Net.Mime.TransferEncoding?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailFormat?displayProperty=fullName>|Рекомендуется использовать <xref:System.Net.Mail.MailMessage.IsBodyHtml%2A?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailMessage?displayProperty=fullName>|Рекомендуется использовать <xref:System.Net.Mail.MailMessage?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailPriority?displayProperty=fullName>|Рекомендуется использовать <xref:System.Net.Mail.MailPriority?displayProperty=fullName>.|  
|<xref:System.Web.Mail.SmtpMail?displayProperty=fullName>|Рекомендуется использовать <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>.|  
|<xref:System.Web.Security.PassportAuthenticationEventArgs?displayProperty=fullName>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](http://go.microsoft.com/fwlink/?LinkId=733413), и в дальнейшем необходимости в ней нет.|  
|<xref:System.Web.Security.PassportAuthenticationEventHandler?displayProperty=fullName>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](http://go.microsoft.com/fwlink/?LinkId=733413), и в дальнейшем необходимости в ней нет.|  
|<xref:System.Web.Security.PassportAuthenticationModule?displayProperty=fullName>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](http://go.microsoft.com/fwlink/?LinkId=733413), и в дальнейшем необходимости в ней нет.|  
|<xref:System.Web.Security.PassportIdentity?displayProperty=fullName>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](http://go.microsoft.com/fwlink/?LinkId=733413), и в дальнейшем необходимости в ней нет.|  
|<xref:System.Web.Security.PassportPrincipal?displayProperty=fullName>|Этот тип устарел. Проверка подлинности паспорта используется однократно при создании [учетной записи Майкрософт](http://go.microsoft.com/fwlink/?LinkId=733413), и в дальнейшем необходимости в ней нет.|  
|<xref:System.Web.UI.ObjectConverter?displayProperty=fullName>|Рекомендуется использовать <xref:System.Convert?displayProperty=fullName> и <xref:System.String.Format%2A?displayProperty=fullName>.|  
  
 [К началу](#introduction)  
  
<a name="mobile"></a>   
### <a name="assembly-systemwebmobiledll"></a>Сборка: System.Web.Mobile.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.Web.Mobile.CookielessData?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.DeviceFilterElement?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.DeviceFilterElementCollection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.DeviceFiltersSection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.ErrorHandlerModule?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileCapabilities?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileDeviceCapabilitiesSectionHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileErrorInfo?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileFormsAuthentication?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.IMobileDesigner?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.IMobileWebFormServices?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.MobileResource?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.Converters.DataFieldConverter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.Converters.DataMemberConverter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.AdRotator?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Alignment?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ArrayListCollectionBase?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.BaseValidator?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.BooleanOption?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Calendar?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Command?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.CommandFormat?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.CompareValidator?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Constants?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ControlElement?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ControlElementCollection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ControlPager?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.CustomValidator?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DesignerAdapterAttribute?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceElement?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceElementCollection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceOverridableAttribute?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecific?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoice?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceCollection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateContainer?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ErrorFormatterPage?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FontInfo?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FontSize?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Form?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FormControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FormMethod?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.IControlAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Image?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.IObjectListFieldCollection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.IPageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ItemPager?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ITemplateable?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Label?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Link?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.List?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListCommandEventArgs?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListCommandEventHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListDataBindEventArgs?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListDataBindEventHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListDecoration?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListSelectType?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralLink?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralText?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralTextContainerControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralTextControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LoadItemsEventArgs?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LoadItemsEventHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControl?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControlsSection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControlsSectionHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileListItem?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileListItemCollection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileListItemType?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobilePage?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileTypeNameConverter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileUserControl?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectList?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommand?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandCollection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventArgs?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventArgs?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListField?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListFieldCollection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListItem?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListItemCollection?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventArgs?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventArgs?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListTitleAttribute?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListViewMode?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PagedControl?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PagerStyle?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Panel?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PanelControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PersistNameAttribute?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PhoneCall?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.RangeValidator?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.RegularExpressionValidator?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.RequiredFieldValidator?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.SelectionList?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Style?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.StyleSheet?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.StyleSheetControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TemplateContainer?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextBox?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextBoxControlBuilder?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextControl?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextView?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextViewElement?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ValidationSummary?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Wrapping?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCalendarAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCommandAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlFormAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlImageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlLinkAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlMobileTextWriter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPhoneCallAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlSelectionListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlTextBoxAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ControlAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCalendarAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCommandAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlControlAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlFormAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlImageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLabelAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLinkAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLiteralTextAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlMobileTextWriter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlObjectListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPanelAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPhoneCallAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlSelectionListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextBoxAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextViewAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidationSummaryAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidatorAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.MobileTextWriter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.MultiPartWriter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlMobileTextWriter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlPageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlCalendarAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlCommandAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlControlAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlFormAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlImageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLabelAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLinkAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLiteralTextAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlMobileTextWriter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlObjectListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPanelAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPhoneCallAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPostFieldType?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlSelectionListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextBoxAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextViewAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidationSummaryAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidatorAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.Doctype?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.StyleSheetLocation?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCalendarAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCommandAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlControlAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCssHandler?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlFormAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlImageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLabelAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLinkAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLiteralTextAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlMobileTextWriter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlObjectListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPageAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPanelAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPhoneCallAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlSelectionListAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextBoxAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextViewAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidationSummaryAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidatorAdapter?displayProperty=fullName>|Сборка System.Web.Mobile.dll не рекомендуется к использованию и больше не должна использоваться. Сведения о разработке мобильных приложений ASP.NET см. в разделе [ASP.NET для мобильных устройств](http://go.microsoft.com/fwlink/?LinkId=157231).|  
  
 [К началу](#introduction)  
  
<a name="workflow_activities"></a>   
### <a name="assembly-systemworkflowactivitiesdll"></a>Сборка: System.Workflow.Activities.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|Все типы из пространства имен <xref:System.Workflow.Activities?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Configuration.ActiveDirectoryRoleFactoryConfiguration?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Rules.RuleActionTrackingEvent?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Rules.RuleConditionReference?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Rules.RuleSetReference?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
  
 [К началу](#introduction)  
  
<a name="workflow_componentmodel"></a>   
### <a name="assembly-systemworkflowcomponentmodeldll"></a>Сборка: System.Workflow.ComponentModel.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|Все типы в пространстве имен <xref:System.Workflow.ComponentModel> кроме <xref:System.Workflow.ComponentModel.GetValueOverride?displayProperty=fullName> и <xref:System.Workflow.ComponentModel.SetValueOverride?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|Все типы в пространстве имен <xref:System.Workflow.ComponentModel.Compiler>, кроме <xref:System.Workflow.ComponentModel.Compiler.ValidationError?displayProperty=fullName> и <xref:System.Workflow.ComponentModel.Compiler.ValidationErrorCollection?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|Все типы в пространстве имен <xref:System.Workflow.ComponentModel.Design>, кроме <xref:System.Workflow.ComponentModel.Design.ConnectorEventHandler>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializationManager?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializer?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityMarkupSerializer?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivitySurrogateSelector?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityTypeCodeDomSerializer?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.CompositeActivityMarkupSerializer?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.DependencyObjectCodeDomSerializer?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
  
 [К началу](#introduction)  
  
<a name="workflow_runtime"></a>   
### <a name="assembly-systemworkflowruntimedll"></a>Сборка: System.Workflow.Runtime.dll  
  
|Тип|Сообщение|  
|----------|-------------| 
|System.Activities.Statements.Interop](assetId:///T:System.Activities.Statements.Interop)|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br />Типы Workflow Foundation 3.0 являются устаревшими. Вместо них используйте типы Workflow 4.0 из <xref:System.Activities>.\*.|  
|<xref:System.Activities.Tracking.InteropTrackingRecord>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br />Типы Workflow Foundation 3.0 являются устаревшими. Вместо них используйте типы Workflow 4.0 из <xref:System.Activities>.\*.|   
|Все типы в пространстве имен <xref:System.Workflow.Runtime>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|Все типы в пространстве имен <xref:System.Workflow.Runtime.Configuration>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|Все типы в пространстве имен <xref:System.Workflow.Runtime.DebugEngine>, кроме <xref:System.Workflow.Runtime.DebugEngine.DebugEngineCallback>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|Все типы в пространстве имен <xref:System.Workflow.Runtime.Hosting>, кроме <xref:System.Workflow.Runtime.Hosting.WorkflowCommitWorkBatchService.CommitWorkBatchCallback>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
|Все типы в пространстве имен <xref:System.Workflow.Runtime.Tracking>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы System.Workflow.\* являются устаревшими. Вместо них используйте новые типы из <xref:System.Activities>.\*.|  
  
 [К началу](#introduction)  
  
<a name="workflowservices"></a>   
### <a name="assembly-systemworkflowservicesdll"></a>Сборка: System.WorkflowServices.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.ServiceModel.WorkflowServiceHost?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Activation.WorkflowServiceHostFactory?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Activities.Description.WorkflowRuntimeEndpoint?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Configuration.ExtendedWorkflowRuntimeServiceElementCollection?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Configuration.PersistenceProviderElement?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Configuration.WorkflowRuntimeElement?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.DurableOperationAttribute?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.DurableServiceAttribute?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.PersistenceProviderBehavior?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.UnknownExceptionAction?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.WorkflowRuntimeBehavior?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Dispatcher.DurableOperationContext?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.InstanceLockException?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.InstanceNotFoundException?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.LockingPersistenceProvider?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.PersistenceException?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.PersistenceProvider?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.PersistenceProviderFactory?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.SqlPersistenceProviderFactory?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|Все типы из пространства имен <xref:System.Workflow.Activities?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Runtime.Hosting.ChannelManagerService?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Типы WF 3 не рекомендуется использовать. Вместо них используйте новые типы WF 4 из <xref:System.Activities>.\*.|  
  
 [К началу](#introduction)  
  
<a name="xaml"></a>   
### <a name="assembly-systemxamldll"></a>Сборка: System.Xaml.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute?displayProperty=fullName>|Не используется синтаксическим анализатором XAML. Просмотрите <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=fullName>.|  
  
 [К началу](#introduction)  
  
<a name="xml"></a>   
### <a name="assembly-systemxmldll"></a>Сборка: System.Xml.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.Xml.IApplicationResourceStreamResolver?displayProperty=fullName>|Первое не рекомендуется на платформе .NET Framework 4.5.<br /><br /> Использование данного типа создает ошибку компилятора.<br /><br /> Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Xml.Schema.XmlSchemaCollection?displayProperty=fullName>|Используйте <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=fullName> для компиляции и проверки схемы.|  
|<xref:System.Xml.XmlValidatingReader?displayProperty=fullName>|Используйте вместо него тип <xref:System.Xml.XmlReader?displayProperty=fullName>, созданный методом <xref:System.Xml.XmlReader.Create%2A?displayProperty=fullName> с использованием соответствующих параметров <xref:System.Xml.XmlReaderSettings?displayProperty=fullName>.|  
|<xref:System.Xml.XmlXapResolver?displayProperty=fullName>|Использование данного типа создает ошибку компилятора. Данный API поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из кода.|  
|<xref:System.Xml.Xsl.XslTransform?displayProperty=fullName>|Этот класс не рекомендуется к использованию. Используйте вместо него <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=fullName>.|  
  
 [К началу](#introduction)  
  
<a name="WindowsBase"></a>   
### <a name="assembly-windowsbasedll"></a>Сборка: WindowsBase.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=fullName>|Тип <xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=fullName> является устаревшим. Этот интерфейс больше не используется.|  
  
 [К началу](#introduction)  
  
<a name="obsolete_types_in_microsoft_assemblies"></a>   
## <a name="obsolete-types-in-microsoft-assemblies"></a>Устаревшие типы в сборках Microsoft  
 В следующих разделах перечислены устаревшие типы в системных сборках корпорации Microsoft. Это сборки специального назначения, например, сборки для конкретного языка (как Microsoft.JScript.dll или Microsoft.VisualC.dll).  
  
<a name="IEHost"></a>   
### <a name="assembly-iehostdll-and-ieexecexe"></a>Сборка: IEHost.dll и IEExec.exe  
 Сборки IEHost.dll и IEExec.exe удалены из платформы .NET Framework. Все их типы и члены устарели и не поддерживаются, начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Эти сборки использовались для размещения элементов управления Windows Forms и для запуска исполняемых файлов в Internet Explorer. Взамен рекомендуется использовать ClickOnce, XAML-приложения браузера (XBAP) и Microsoft Silverlight.  
  
 [К началу](#introduction)  
  
<a name="Engine"></a>   
### <a name="assembly-microsoftbuildenginedll"></a>Сборка: Microsoft.Build.Engine.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=fullName>|Этот класс не рекомендуется к использованию. Используйте вместо него <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName> из сборки <!--zz <xref:Microsoft.Build?displayProperty=fullName> -->``Microsoft.Build`.|  
|<xref:Microsoft.Build.BuildEngine.Project?displayProperty=fullName>|Этот класс не рекомендуется к использованию. Используйте вместо него <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName> из сборки <xref:Microsoft.Build?displayProperty=fullName>.|  
  
 [К началу](#introduction)  
  
<a name="jscript"></a>   
### <a name="assembly-microsoftjscriptdll"></a>Сборка: Microsoft.JScript.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:Microsoft.JScript.Vsa.BaseVsaEngine?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.BaseVsaSite?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.BaseVsaStartup?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaCodeItem?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaEngine?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaError?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaGlobalItem?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaItem?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaItems?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaPersistSite?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaReferenceItem?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaSite?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.JSVsaError?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.JSVsaException?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.JSVsaItemFlag?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.JSVsaItemType?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.ResInfo?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.VsaEngine?displayProperty=fullName>|Использование этого типа не рекомендуется, поскольку он не рекомендован к использованию в Visual Studio 2005; замена данной возможности не планируется. Дополнительные справочные сведения см. в документации <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
  
 [К началу](#introduction)  
  
<a name="VBCompat"></a>   
### <a name="assembly-microsoftvisualbasiccompatibilitydll"></a>Сборка: Microsoft.VisualBasic.Compatibility.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseControlArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseOcxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ButtonArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckedListBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ColorDialogArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ComboBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBox?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBox?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBox?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FixedLengthString?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FontDialogArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FormShowConstants?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.GroupBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.HScrollBarArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ImageListArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LabelArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxItem?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListViewArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LoadResConstants?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MaskedTextBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MenuItemArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MouseButtonConstants?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.OpenFileDialogArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PanelArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PictureBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PrintDialogArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ProgressBarArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RadioButtonArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RichTextBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SaveFileDialogArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ScaleMode?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ShiftConstants?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusBarArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusStripArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.Support?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TabControlArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TextBoxArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TimerArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolBarArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripMenuItemArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TreeViewArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.VScrollBarArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebBrowserArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClass?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassContainingClassNotOptional?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassCouldNotFindEvent?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemCannotBeCurrentWebItem?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemRespondNotFound?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassUserWebClassNameNotOptional?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebClassFileNameNotOptional?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebItemNotValid?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItem?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemAssociatedWebClassNotOptional?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemClosingTagNotFound?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadEmbeddedResource?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadTemplateFile?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNameNotOptional?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNoTemplateSpecified?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemTooManyNestedTags?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemUnexpectedErrorReadingTemplateFile?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ZOrderConstants?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
  
 [К началу](#introduction)  
  
<a name="VBCompatData"></a>   
### <a name="assembly-microsoftvisualbasiccompatibilitydatadll"></a>Сборка: Microsoft.VisualBasic.Compatibility.Data.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.BOFActionEnum?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EndOfRecordsetDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EOFActionEnum?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.ErrorDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchCompleteDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchProgressDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FieldChangeCompleteDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.MoveCompleteDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.OrientationEnum?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordChangeCompleteDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordsetChangeCompleteDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeFieldDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordsetDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillMoveDelegate?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODCArray?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseDataEnvironment?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BindingCollectionEnumerator?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CONNECTDATA?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBBINDING?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBCOLUMNINFO?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBID?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBinding?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBindingCollection?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBKINDENUM?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBPROPIDSET?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IAccessor?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IChapteredRowset?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IColumnsInfo?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPoint?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPointContainer?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormat?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormatDisp?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnectionPoints?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnections?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPosition?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPositionChange?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowset?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetChange?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetIdentity?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetInfo?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetNotify?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBinding?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBindingCollection?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SRDescriptionAttribute?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UGUID?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UNAME?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UpdateMode?displayProperty=fullName>|См. раздел [Microsoft.VisualBasic.Compatibility.VB6.<элемент>\< устарел и поддерживается только в 32-разрядных процессах](https://msdn.microsoft.com/library/ee839621.aspx).|  
  
 [К началу](#introduction)  
  
<a name="visualc"></a>   
### <a name="assembly-microsoftvisualcdll"></a>Сборка: Microsoft.VisualC.dll  
  
|Тип|Сообщение|  
|----------|-------------|  
|<xref:Microsoft.VisualC.DebugInfoInPDBAttribute?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
|<xref:Microsoft.VisualC.DecoratedNameAttribute?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
|<xref:Microsoft.VisualC.IsConstModifier?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
|<xref:Microsoft.VisualC.IsCXXReferenceModifier?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
|<xref:Microsoft.VisualC.IsLongModifier?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
|<xref:Microsoft.VisualC.IsSignedModifier?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
|<xref:Microsoft.VisualC.IsVolatileModifier?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
|<xref:Microsoft.VisualC.MiscellaneousBitsAttribute?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
|<xref:Microsoft.VisualC.NeedsCopyConstructorModifier?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
|<xref:Microsoft.VisualC.NoSignSpecifiedModifier?displayProperty=fullName>|Сборка Microsoft.VisualC.dll устарела и существует только из соображений обратной совместимости.|  
  
## <a name="see-also"></a>См. также  
 [Устаревшие классы библиотеки классов](../../../docs/framework/whats-new/whats-obsolete.md)   
 [Устаревшие члены](../../../docs/framework/whats-new/obsolete-members.md)

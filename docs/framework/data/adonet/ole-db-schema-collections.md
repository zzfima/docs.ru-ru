---
title: "Коллекции схемы OLE DB"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9b88308c5dad69ed1ba6f48f525931e94f13ef1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="1090a-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="1090a-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="1090a-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="1090a-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="1090a-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="1090a-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="1090a-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем:</span><span class="sxs-lookup"><span data-stu-id="1090a-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="1090a-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="1090a-106">Tables</span></span>  
  
-   <span data-ttu-id="1090a-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="1090a-107">Columns</span></span>  
  
-   <span data-ttu-id="1090a-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="1090a-108">Procedures</span></span>  
  
-   <span data-ttu-id="1090a-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1090a-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="1090a-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="1090a-110">Catalog</span></span>  
  
-   <span data-ttu-id="1090a-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="1090a-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1090a-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="1090a-112">Tables</span></span>  
  
|<span data-ttu-id="1090a-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-113">ColumnName</span></span>|<span data-ttu-id="1090a-114">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-115">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-116">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-116">String</span></span>|  
|<span data-ttu-id="1090a-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-118">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-118">String</span></span>|  
|<span data-ttu-id="1090a-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-119">TABLE_NAME</span></span>|<span data-ttu-id="1090a-120">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-120">String</span></span>|  
|<span data-ttu-id="1090a-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-121">TABLE_TYPE</span></span>|<span data-ttu-id="1090a-122">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-122">String</span></span>|  
|<span data-ttu-id="1090a-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-123">TABLE_GUID</span></span>|<span data-ttu-id="1090a-124">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-124">Guid</span></span>|  
|<span data-ttu-id="1090a-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-125">DESCRIPTION</span></span>|<span data-ttu-id="1090a-126">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-126">String</span></span>|  
|<span data-ttu-id="1090a-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-127">TABLE_PROPID</span></span>|<span data-ttu-id="1090a-128">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-128">Int64</span></span>|  
|<span data-ttu-id="1090a-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1090a-129">DATE_CREATED</span></span>|<span data-ttu-id="1090a-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-130">DateTime</span></span>|  
|<span data-ttu-id="1090a-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1090a-131">DATE_MODIFIED</span></span>|<span data-ttu-id="1090a-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1090a-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="1090a-133">Columns</span></span>  
  
|<span data-ttu-id="1090a-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-134">ColumnName</span></span>|<span data-ttu-id="1090a-135">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-136">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-137">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-137">String</span></span>|  
|<span data-ttu-id="1090a-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-139">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-139">String</span></span>|  
|<span data-ttu-id="1090a-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-140">TABLE_NAME</span></span>|<span data-ttu-id="1090a-141">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-141">String</span></span>|  
|<span data-ttu-id="1090a-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-142">COLUMN_NAME</span></span>|<span data-ttu-id="1090a-143">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-143">String</span></span>|  
|<span data-ttu-id="1090a-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-144">COLUMN_GUID</span></span>|<span data-ttu-id="1090a-145">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-145">Guid</span></span>|  
|<span data-ttu-id="1090a-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-146">COLUMN_PROPID</span></span>|<span data-ttu-id="1090a-147">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-147">Int64</span></span>|  
|<span data-ttu-id="1090a-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1090a-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="1090a-149">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-149">Int64</span></span>|  
|<span data-ttu-id="1090a-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1090a-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1090a-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-151">Boolean</span></span>|  
|<span data-ttu-id="1090a-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1090a-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1090a-153">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-153">String</span></span>|  
|<span data-ttu-id="1090a-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1090a-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="1090a-155">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-155">Int64</span></span>|  
|<span data-ttu-id="1090a-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1090a-156">IS_NULLABLE</span></span>|<span data-ttu-id="1090a-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-157">Boolean</span></span>|  
|<span data-ttu-id="1090a-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-158">DATA_TYPE</span></span>|<span data-ttu-id="1090a-159">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-159">Int32</span></span>|  
|<span data-ttu-id="1090a-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-160">TYPE_GUID</span></span>|<span data-ttu-id="1090a-161">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-161">Guid</span></span>|  
|<span data-ttu-id="1090a-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1090a-163">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-163">Int64</span></span>|  
|<span data-ttu-id="1090a-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1090a-165">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-165">Int64</span></span>|  
|<span data-ttu-id="1090a-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1090a-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1090a-167">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-167">Int32</span></span>|  
|<span data-ttu-id="1090a-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1090a-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="1090a-169">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-169">Int16</span></span>|  
|<span data-ttu-id="1090a-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1090a-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="1090a-171">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-171">Int64</span></span>|  
|<span data-ttu-id="1090a-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1090a-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-173">String</span></span>|  
|<span data-ttu-id="1090a-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1090a-175">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-175">String</span></span>|  
|<span data-ttu-id="1090a-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1090a-177">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-177">String</span></span>|  
|<span data-ttu-id="1090a-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="1090a-179">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-179">String</span></span>|  
|<span data-ttu-id="1090a-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1090a-181">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-181">String</span></span>|  
|<span data-ttu-id="1090a-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-182">COLLATION_NAME</span></span>|<span data-ttu-id="1090a-183">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-183">String</span></span>|  
|<span data-ttu-id="1090a-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1090a-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-185">String</span></span>|  
|<span data-ttu-id="1090a-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1090a-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-187">String</span></span>|  
|<span data-ttu-id="1090a-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-188">DOMAIN_NAME</span></span>|<span data-ttu-id="1090a-189">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-189">String</span></span>|  
|<span data-ttu-id="1090a-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-190">DESCRIPTION</span></span>|<span data-ttu-id="1090a-191">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-191">String</span></span>|  
|<span data-ttu-id="1090a-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="1090a-192">COLUMN_LCID</span></span>|<span data-ttu-id="1090a-193">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-193">Int32</span></span>|  
|<span data-ttu-id="1090a-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="1090a-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="1090a-195">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-195">Int32</span></span>|  
|<span data-ttu-id="1090a-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="1090a-196">COLUMN_SORTID</span></span>|<span data-ttu-id="1090a-197">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-197">Int32</span></span>|  
|<span data-ttu-id="1090a-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="1090a-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="1090a-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="1090a-199">Byte[]</span></span>|  
|<span data-ttu-id="1090a-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="1090a-200">IS_COMPUTED</span></span>|<span data-ttu-id="1090a-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1090a-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="1090a-202">Procedures</span></span>  
  
|<span data-ttu-id="1090a-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-203">ColumnName</span></span>|<span data-ttu-id="1090a-204">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1090a-206">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-206">String</span></span>|  
|<span data-ttu-id="1090a-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1090a-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-208">String</span></span>|  
|<span data-ttu-id="1090a-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="1090a-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-210">String</span></span>|  
|<span data-ttu-id="1090a-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1090a-212">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-212">Int16</span></span>|  
|<span data-ttu-id="1090a-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1090a-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1090a-214">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-214">String</span></span>|  
|<span data-ttu-id="1090a-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-215">DESCRIPTION</span></span>|<span data-ttu-id="1090a-216">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-216">String</span></span>|  
|<span data-ttu-id="1090a-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1090a-217">DATE_CREATED</span></span>|<span data-ttu-id="1090a-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-218">DateTime</span></span>|  
|<span data-ttu-id="1090a-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1090a-219">DATE_MODIFIED</span></span>|<span data-ttu-id="1090a-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="1090a-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1090a-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="1090a-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-222">ColumnName</span></span>|<span data-ttu-id="1090a-223">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1090a-225">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-225">String</span></span>|  
|<span data-ttu-id="1090a-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1090a-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-227">String</span></span>|  
|<span data-ttu-id="1090a-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="1090a-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-229">String</span></span>|  
|<span data-ttu-id="1090a-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-230">PARAMETER_NAME</span></span>|<span data-ttu-id="1090a-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-231">String</span></span>|  
|<span data-ttu-id="1090a-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1090a-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="1090a-233">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-233">Int32</span></span>|  
|<span data-ttu-id="1090a-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="1090a-235">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-235">Int32</span></span>|  
|<span data-ttu-id="1090a-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1090a-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="1090a-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-237">Boolean</span></span>|  
|<span data-ttu-id="1090a-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1090a-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="1090a-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-239">String</span></span>|  
|<span data-ttu-id="1090a-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1090a-240">IS_NULLABLE</span></span>|<span data-ttu-id="1090a-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-241">Boolean</span></span>|  
|<span data-ttu-id="1090a-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-242">DATA_TYPE</span></span>|<span data-ttu-id="1090a-243">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-243">Int32</span></span>|  
|<span data-ttu-id="1090a-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1090a-245">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-245">Int64</span></span>|  
|<span data-ttu-id="1090a-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1090a-247">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-247">Int64</span></span>|  
|<span data-ttu-id="1090a-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1090a-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1090a-249">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-249">Int32</span></span>|  
|<span data-ttu-id="1090a-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1090a-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="1090a-251">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-251">Int16</span></span>|  
|<span data-ttu-id="1090a-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-252">DESCRIPTION</span></span>|<span data-ttu-id="1090a-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-253">String</span></span>|  
|<span data-ttu-id="1090a-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-254">TYPE_NAME</span></span>|<span data-ttu-id="1090a-255">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-255">String</span></span>|  
|<span data-ttu-id="1090a-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="1090a-257">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="1090a-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="1090a-258">Catalog</span></span>  
  
|<span data-ttu-id="1090a-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-259">ColumnName</span></span>|<span data-ttu-id="1090a-260">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-261">CATALOG_NAME</span></span>|<span data-ttu-id="1090a-262">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-262">String</span></span>|  
|<span data-ttu-id="1090a-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-263">DESCRIPTION</span></span>|<span data-ttu-id="1090a-264">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1090a-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="1090a-265">Indexes</span></span>  
  
|<span data-ttu-id="1090a-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-266">ColumnName</span></span>|<span data-ttu-id="1090a-267">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-268">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-269">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-269">String</span></span>|  
|<span data-ttu-id="1090a-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-271">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-271">String</span></span>|  
|<span data-ttu-id="1090a-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-272">TABLE_NAME</span></span>|<span data-ttu-id="1090a-273">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-273">String</span></span>|  
|<span data-ttu-id="1090a-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-274">INDEX_CATALOG</span></span>|<span data-ttu-id="1090a-275">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-275">String</span></span>|  
|<span data-ttu-id="1090a-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="1090a-277">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-277">String</span></span>|  
|<span data-ttu-id="1090a-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-278">INDEX_NAME</span></span>|<span data-ttu-id="1090a-279">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-279">String</span></span>|  
|<span data-ttu-id="1090a-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1090a-280">PRIMARY_KEY</span></span>|<span data-ttu-id="1090a-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-281">Boolean</span></span>|  
|<span data-ttu-id="1090a-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1090a-282">UNIQUE</span></span>|<span data-ttu-id="1090a-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-283">Boolean</span></span>|  
|<span data-ttu-id="1090a-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1090a-284">CLUSTERED</span></span>|<span data-ttu-id="1090a-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-285">Boolean</span></span>|  
|<span data-ttu-id="1090a-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-286">TYPE</span></span>|<span data-ttu-id="1090a-287">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-287">Int32</span></span>|  
|<span data-ttu-id="1090a-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1090a-288">FILL_FACTOR</span></span>|<span data-ttu-id="1090a-289">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-289">Int32</span></span>|  
|<span data-ttu-id="1090a-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1090a-290">INITIAL_SIZE</span></span>|<span data-ttu-id="1090a-291">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-291">Int32</span></span>|  
|<span data-ttu-id="1090a-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="1090a-292">NULLS</span></span>|<span data-ttu-id="1090a-293">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-293">Int32</span></span>|  
|<span data-ttu-id="1090a-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1090a-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1090a-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-295">Boolean</span></span>|  
|<span data-ttu-id="1090a-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1090a-296">AUTO_UPDATE</span></span>|<span data-ttu-id="1090a-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-297">Boolean</span></span>|  
|<span data-ttu-id="1090a-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1090a-298">NULL_COLLATION</span></span>|<span data-ttu-id="1090a-299">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-299">Int32</span></span>|  
|<span data-ttu-id="1090a-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1090a-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="1090a-301">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-301">Int64</span></span>|  
|<span data-ttu-id="1090a-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-302">COLUMN_NAME</span></span>|<span data-ttu-id="1090a-303">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-303">String</span></span>|  
|<span data-ttu-id="1090a-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-304">COLUMN_GUID</span></span>|<span data-ttu-id="1090a-305">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-305">Guid</span></span>|  
|<span data-ttu-id="1090a-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-306">COLUMN_PROPID</span></span>|<span data-ttu-id="1090a-307">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-307">Int64</span></span>|  
|<span data-ttu-id="1090a-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1090a-308">COLLATION</span></span>|<span data-ttu-id="1090a-309">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-309">Int16</span></span>|  
|<span data-ttu-id="1090a-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1090a-310">CARDINALITY</span></span>|<span data-ttu-id="1090a-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="1090a-311">Decimal</span></span>|  
|<span data-ttu-id="1090a-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="1090a-312">PAGES</span></span>|<span data-ttu-id="1090a-313">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-313">Int32</span></span>|  
|<span data-ttu-id="1090a-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1090a-314">FILTER_CONDITION</span></span>|<span data-ttu-id="1090a-315">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-315">String</span></span>|  
|<span data-ttu-id="1090a-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1090a-316">INTEGRATED</span></span>|<span data-ttu-id="1090a-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="1090a-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="1090a-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="1090a-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="1090a-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="1090a-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="1090a-320">Tables</span></span>  
  
-   <span data-ttu-id="1090a-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="1090a-321">Columns</span></span>  
  
-   <span data-ttu-id="1090a-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="1090a-322">Procedures</span></span>  
  
-   <span data-ttu-id="1090a-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="1090a-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="1090a-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1090a-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="1090a-325">Представления</span><span class="sxs-lookup"><span data-stu-id="1090a-325">Views</span></span>  
  
-   <span data-ttu-id="1090a-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="1090a-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1090a-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="1090a-327">Tables</span></span>  
  
|<span data-ttu-id="1090a-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-328">ColumnName</span></span>|<span data-ttu-id="1090a-329">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-330">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-331">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-331">String</span></span>|  
|<span data-ttu-id="1090a-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-333">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-333">String</span></span>|  
|<span data-ttu-id="1090a-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-334">TABLE_NAME</span></span>|<span data-ttu-id="1090a-335">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-335">String</span></span>|  
|<span data-ttu-id="1090a-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-336">TABLE_TYPE</span></span>|<span data-ttu-id="1090a-337">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-337">String</span></span>|  
|<span data-ttu-id="1090a-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-338">TABLE_GUID</span></span>|<span data-ttu-id="1090a-339">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-339">Guid</span></span>|  
|<span data-ttu-id="1090a-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-340">DESCRIPTION</span></span>|<span data-ttu-id="1090a-341">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-341">String</span></span>|  
|<span data-ttu-id="1090a-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-342">TABLE_PROPID</span></span>|<span data-ttu-id="1090a-343">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-343">Int64</span></span>|  
|<span data-ttu-id="1090a-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1090a-344">DATE_CREATED</span></span>|<span data-ttu-id="1090a-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-345">DateTime</span></span>|  
|<span data-ttu-id="1090a-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1090a-346">DATE_MODIFIED</span></span>|<span data-ttu-id="1090a-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1090a-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="1090a-348">Columns</span></span>  
  
|<span data-ttu-id="1090a-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-349">ColumnName</span></span>|<span data-ttu-id="1090a-350">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-351">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-352">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-352">String</span></span>|  
|<span data-ttu-id="1090a-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-354">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-354">String</span></span>|  
|<span data-ttu-id="1090a-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-355">TABLE_NAME</span></span>|<span data-ttu-id="1090a-356">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-356">String</span></span>|  
|<span data-ttu-id="1090a-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-357">COLUMN_NAME</span></span>|<span data-ttu-id="1090a-358">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-358">String</span></span>|  
|<span data-ttu-id="1090a-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-359">COLUMN_GUID</span></span>|<span data-ttu-id="1090a-360">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-360">Guid</span></span>|  
|<span data-ttu-id="1090a-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-361">COLUMN_PROPID</span></span>|<span data-ttu-id="1090a-362">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-362">Int64</span></span>|  
|<span data-ttu-id="1090a-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1090a-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="1090a-364">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-364">Int64</span></span>|  
|<span data-ttu-id="1090a-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1090a-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1090a-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-366">Boolean</span></span>|  
|<span data-ttu-id="1090a-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1090a-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1090a-368">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-368">String</span></span>|  
|<span data-ttu-id="1090a-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1090a-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="1090a-370">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-370">Int64</span></span>|  
|<span data-ttu-id="1090a-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1090a-371">IS_NULLABLE</span></span>|<span data-ttu-id="1090a-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-372">Boolean</span></span>|  
|<span data-ttu-id="1090a-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-373">DATA_TYPE</span></span>|<span data-ttu-id="1090a-374">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-374">Int32</span></span>|  
|<span data-ttu-id="1090a-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-375">TYPE_GUID</span></span>|<span data-ttu-id="1090a-376">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-376">Guid</span></span>|  
|<span data-ttu-id="1090a-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1090a-378">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-378">Int64</span></span>|  
|<span data-ttu-id="1090a-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1090a-380">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-380">Int64</span></span>|  
|<span data-ttu-id="1090a-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1090a-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1090a-382">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-382">Int32</span></span>|  
|<span data-ttu-id="1090a-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1090a-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="1090a-384">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-384">Int16</span></span>|  
|<span data-ttu-id="1090a-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1090a-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="1090a-386">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-386">Int64</span></span>|  
|<span data-ttu-id="1090a-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1090a-388">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-388">String</span></span>|  
|<span data-ttu-id="1090a-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1090a-390">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-390">String</span></span>|  
|<span data-ttu-id="1090a-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1090a-392">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-392">String</span></span>|  
|<span data-ttu-id="1090a-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="1090a-394">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-394">String</span></span>|  
|<span data-ttu-id="1090a-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1090a-396">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-396">String</span></span>|  
|<span data-ttu-id="1090a-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-397">COLLATION_NAME</span></span>|<span data-ttu-id="1090a-398">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-398">String</span></span>|  
|<span data-ttu-id="1090a-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1090a-400">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-400">String</span></span>|  
|<span data-ttu-id="1090a-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1090a-402">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-402">String</span></span>|  
|<span data-ttu-id="1090a-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-403">DOMAIN_NAME</span></span>|<span data-ttu-id="1090a-404">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-404">String</span></span>|  
|<span data-ttu-id="1090a-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-405">DESCRIPTION</span></span>|<span data-ttu-id="1090a-406">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1090a-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="1090a-407">Procedures</span></span>  
  
|<span data-ttu-id="1090a-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-408">ColumnName</span></span>|<span data-ttu-id="1090a-409">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1090a-411">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-411">String</span></span>|  
|<span data-ttu-id="1090a-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1090a-413">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-413">String</span></span>|  
|<span data-ttu-id="1090a-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="1090a-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-415">String</span></span>|  
|<span data-ttu-id="1090a-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1090a-417">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-417">Int16</span></span>|  
|<span data-ttu-id="1090a-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1090a-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1090a-419">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-419">String</span></span>|  
|<span data-ttu-id="1090a-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-420">DESCRIPTION</span></span>|<span data-ttu-id="1090a-421">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-421">String</span></span>|  
|<span data-ttu-id="1090a-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1090a-422">DATE_CREATED</span></span>|<span data-ttu-id="1090a-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-423">DateTime</span></span>|  
|<span data-ttu-id="1090a-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1090a-424">DATE_MODIFIED</span></span>|<span data-ttu-id="1090a-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="1090a-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="1090a-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="1090a-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-427">ColumnName</span></span>|<span data-ttu-id="1090a-428">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1090a-430">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-430">String</span></span>|  
|<span data-ttu-id="1090a-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1090a-432">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-432">String</span></span>|  
|<span data-ttu-id="1090a-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="1090a-434">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-434">String</span></span>|  
|<span data-ttu-id="1090a-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-435">COLUMN_NAME</span></span>|<span data-ttu-id="1090a-436">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-436">String</span></span>|  
|<span data-ttu-id="1090a-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-437">COLUMN_GUID</span></span>|<span data-ttu-id="1090a-438">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-438">Guid</span></span>|  
|<span data-ttu-id="1090a-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-439">COLUMN_PROPID</span></span>|<span data-ttu-id="1090a-440">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-440">Int64</span></span>|  
|<span data-ttu-id="1090a-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="1090a-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="1090a-442">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-442">Int64</span></span>|  
|<span data-ttu-id="1090a-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1090a-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="1090a-444">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-444">Int64</span></span>|  
|<span data-ttu-id="1090a-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1090a-445">IS_NULLABLE</span></span>|<span data-ttu-id="1090a-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-446">Boolean</span></span>|  
|<span data-ttu-id="1090a-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-447">DATA_TYPE</span></span>|<span data-ttu-id="1090a-448">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-448">Int32</span></span>|  
|<span data-ttu-id="1090a-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-449">TYPE_GUID</span></span>|<span data-ttu-id="1090a-450">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-450">Guid</span></span>|  
|<span data-ttu-id="1090a-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1090a-452">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-452">Int64</span></span>|  
|<span data-ttu-id="1090a-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1090a-454">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-454">Int64</span></span>|  
|<span data-ttu-id="1090a-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1090a-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1090a-456">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-456">Int32</span></span>|  
|<span data-ttu-id="1090a-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1090a-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="1090a-458">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-458">Int16</span></span>|  
|<span data-ttu-id="1090a-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-459">DESCRIPTION</span></span>|<span data-ttu-id="1090a-460">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-460">String</span></span>|  
|<span data-ttu-id="1090a-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="1090a-461">OVERLOAD</span></span>|<span data-ttu-id="1090a-462">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1090a-463">Представления</span><span class="sxs-lookup"><span data-stu-id="1090a-463">Views</span></span>  
  
|<span data-ttu-id="1090a-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-464">ColumnName</span></span>|<span data-ttu-id="1090a-465">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-466">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-467">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-467">String</span></span>|  
|<span data-ttu-id="1090a-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-469">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-469">String</span></span>|  
|<span data-ttu-id="1090a-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-470">TABLE_NAME</span></span>|<span data-ttu-id="1090a-471">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-471">String</span></span>|  
|<span data-ttu-id="1090a-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1090a-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="1090a-473">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-473">String</span></span>|  
|<span data-ttu-id="1090a-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-474">CHECK_OPTION</span></span>|<span data-ttu-id="1090a-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-475">Boolean</span></span>|  
|<span data-ttu-id="1090a-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="1090a-476">IS_UPDATABLE</span></span>|<span data-ttu-id="1090a-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-477">Boolean</span></span>|  
|<span data-ttu-id="1090a-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-478">DESCRIPTION</span></span>|<span data-ttu-id="1090a-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-479">String</span></span>|  
|<span data-ttu-id="1090a-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1090a-480">DATE_CREATED</span></span>|<span data-ttu-id="1090a-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-481">DateTime</span></span>|  
|<span data-ttu-id="1090a-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1090a-482">DATE_MODIFIED</span></span>|<span data-ttu-id="1090a-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1090a-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="1090a-484">Indexes</span></span>  
  
|<span data-ttu-id="1090a-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-485">ColumnName</span></span>|<span data-ttu-id="1090a-486">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-487">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-488">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-488">String</span></span>|  
|<span data-ttu-id="1090a-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-490">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-490">String</span></span>|  
|<span data-ttu-id="1090a-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-491">TABLE_NAME</span></span>|<span data-ttu-id="1090a-492">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-492">String</span></span>|  
|<span data-ttu-id="1090a-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-493">INDEX_CATALOG</span></span>|<span data-ttu-id="1090a-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-494">String</span></span>|  
|<span data-ttu-id="1090a-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="1090a-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-496">String</span></span>|  
|<span data-ttu-id="1090a-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-497">INDEX_NAME</span></span>|<span data-ttu-id="1090a-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-498">String</span></span>|  
|<span data-ttu-id="1090a-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1090a-499">PRIMARY_KEY</span></span>|<span data-ttu-id="1090a-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-500">Boolean</span></span>|  
|<span data-ttu-id="1090a-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1090a-501">UNIQUE</span></span>|<span data-ttu-id="1090a-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-502">Boolean</span></span>|  
|<span data-ttu-id="1090a-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1090a-503">CLUSTERED</span></span>|<span data-ttu-id="1090a-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-504">Boolean</span></span>|  
|<span data-ttu-id="1090a-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-505">TYPE</span></span>|<span data-ttu-id="1090a-506">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-506">Int32</span></span>|  
|<span data-ttu-id="1090a-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1090a-507">FILL_FACTOR</span></span>|<span data-ttu-id="1090a-508">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-508">Int32</span></span>|  
|<span data-ttu-id="1090a-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1090a-509">INITIAL_SIZE</span></span>|<span data-ttu-id="1090a-510">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-510">Int32</span></span>|  
|<span data-ttu-id="1090a-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="1090a-511">NULLS</span></span>|<span data-ttu-id="1090a-512">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-512">Int32</span></span>|  
|<span data-ttu-id="1090a-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1090a-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1090a-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-514">Boolean</span></span>|  
|<span data-ttu-id="1090a-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1090a-515">AUTO_UPDATE</span></span>|<span data-ttu-id="1090a-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-516">Boolean</span></span>|  
|<span data-ttu-id="1090a-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1090a-517">NULL_COLLATION</span></span>|<span data-ttu-id="1090a-518">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-518">Int32</span></span>|  
|<span data-ttu-id="1090a-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1090a-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="1090a-520">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-520">Int64</span></span>|  
|<span data-ttu-id="1090a-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-521">COLUMN_NAME</span></span>|<span data-ttu-id="1090a-522">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-522">String</span></span>|  
|<span data-ttu-id="1090a-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-523">COLUMN_GUID</span></span>|<span data-ttu-id="1090a-524">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-524">Guid</span></span>|  
|<span data-ttu-id="1090a-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-525">COLUMN_PROPID</span></span>|<span data-ttu-id="1090a-526">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-526">Int64</span></span>|  
|<span data-ttu-id="1090a-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1090a-527">COLLATION</span></span>|<span data-ttu-id="1090a-528">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-528">Int16</span></span>|  
|<span data-ttu-id="1090a-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1090a-529">CARDINALITY</span></span>|<span data-ttu-id="1090a-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="1090a-530">Decimal</span></span>|  
|<span data-ttu-id="1090a-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="1090a-531">PAGES</span></span>|<span data-ttu-id="1090a-532">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-532">Int32</span></span>|  
|<span data-ttu-id="1090a-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1090a-533">FILTER_CONDITION</span></span>|<span data-ttu-id="1090a-534">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-534">String</span></span>|  
|<span data-ttu-id="1090a-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1090a-535">INTEGRATED</span></span>|<span data-ttu-id="1090a-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="1090a-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="1090a-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="1090a-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="1090a-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="1090a-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="1090a-539">Tables</span></span>  
  
-   <span data-ttu-id="1090a-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="1090a-540">Columns</span></span>  
  
-   <span data-ttu-id="1090a-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="1090a-541">Procedures</span></span>  
  
-   <span data-ttu-id="1090a-542">Представления</span><span class="sxs-lookup"><span data-stu-id="1090a-542">Views</span></span>  
  
-   <span data-ttu-id="1090a-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="1090a-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1090a-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="1090a-544">Tables</span></span>  
  
|<span data-ttu-id="1090a-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-545">ColumnName</span></span>|<span data-ttu-id="1090a-546">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-547">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-548">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-548">String</span></span>|  
|<span data-ttu-id="1090a-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-550">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-550">String</span></span>|  
|<span data-ttu-id="1090a-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-551">TABLE_NAME</span></span>|<span data-ttu-id="1090a-552">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-552">String</span></span>|  
|<span data-ttu-id="1090a-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-553">TABLE_TYPE</span></span>|<span data-ttu-id="1090a-554">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-554">String</span></span>|  
|<span data-ttu-id="1090a-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-555">TABLE_GUID</span></span>|<span data-ttu-id="1090a-556">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-556">Guid</span></span>|  
|<span data-ttu-id="1090a-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-557">DESCRIPTION</span></span>|<span data-ttu-id="1090a-558">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-558">String</span></span>|  
|<span data-ttu-id="1090a-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-559">TABLE_PROPID</span></span>|<span data-ttu-id="1090a-560">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-560">Int64</span></span>|  
|<span data-ttu-id="1090a-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1090a-561">DATE_CREATED</span></span>|<span data-ttu-id="1090a-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-562">DateTime</span></span>|  
|<span data-ttu-id="1090a-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1090a-563">DATE_MODIFIED</span></span>|<span data-ttu-id="1090a-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1090a-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="1090a-565">Columns</span></span>  
  
|<span data-ttu-id="1090a-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-566">ColumnName</span></span>|<span data-ttu-id="1090a-567">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-568">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-569">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-569">String</span></span>|  
|<span data-ttu-id="1090a-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-571">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-571">String</span></span>|  
|<span data-ttu-id="1090a-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-572">TABLE_NAME</span></span>|<span data-ttu-id="1090a-573">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-573">String</span></span>|  
|<span data-ttu-id="1090a-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-574">COLUMN_NAME</span></span>|<span data-ttu-id="1090a-575">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-575">String</span></span>|  
|<span data-ttu-id="1090a-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-576">COLUMN_GUID</span></span>|<span data-ttu-id="1090a-577">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-577">Guid</span></span>|  
|<span data-ttu-id="1090a-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-578">COLUMN_PROPID</span></span>|<span data-ttu-id="1090a-579">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-579">Int64</span></span>|  
|<span data-ttu-id="1090a-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1090a-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="1090a-581">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-581">Int64</span></span>|  
|<span data-ttu-id="1090a-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1090a-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1090a-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-583">Boolean</span></span>|  
|<span data-ttu-id="1090a-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1090a-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1090a-585">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-585">String</span></span>|  
|<span data-ttu-id="1090a-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1090a-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="1090a-587">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-587">Int64</span></span>|  
|<span data-ttu-id="1090a-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1090a-588">IS_NULLABLE</span></span>|<span data-ttu-id="1090a-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-589">Boolean</span></span>|  
|<span data-ttu-id="1090a-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-590">DATA_TYPE</span></span>|<span data-ttu-id="1090a-591">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-591">Int32</span></span>|  
|<span data-ttu-id="1090a-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-592">TYPE_GUID</span></span>|<span data-ttu-id="1090a-593">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-593">Guid</span></span>|  
|<span data-ttu-id="1090a-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1090a-595">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-595">Int64</span></span>|  
|<span data-ttu-id="1090a-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1090a-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1090a-597">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-597">Int64</span></span>|  
|<span data-ttu-id="1090a-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1090a-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1090a-599">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-599">Int32</span></span>|  
|<span data-ttu-id="1090a-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1090a-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="1090a-601">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-601">Int16</span></span>|  
|<span data-ttu-id="1090a-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1090a-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="1090a-603">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-603">Int64</span></span>|  
|<span data-ttu-id="1090a-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1090a-605">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-605">String</span></span>|  
|<span data-ttu-id="1090a-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1090a-607">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-607">String</span></span>|  
|<span data-ttu-id="1090a-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1090a-609">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-609">String</span></span>|  
|<span data-ttu-id="1090a-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="1090a-611">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-611">String</span></span>|  
|<span data-ttu-id="1090a-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1090a-613">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-613">String</span></span>|  
|<span data-ttu-id="1090a-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-614">COLLATION_NAME</span></span>|<span data-ttu-id="1090a-615">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-615">String</span></span>|  
|<span data-ttu-id="1090a-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1090a-617">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-617">String</span></span>|  
|<span data-ttu-id="1090a-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1090a-619">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-619">String</span></span>|  
|<span data-ttu-id="1090a-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-620">DOMAIN_NAME</span></span>|<span data-ttu-id="1090a-621">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-621">String</span></span>|  
|<span data-ttu-id="1090a-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-622">DESCRIPTION</span></span>|<span data-ttu-id="1090a-623">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1090a-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="1090a-624">Procedures</span></span>  
  
|<span data-ttu-id="1090a-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-625">ColumnName</span></span>|<span data-ttu-id="1090a-626">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1090a-628">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-628">String</span></span>|  
|<span data-ttu-id="1090a-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1090a-630">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-630">String</span></span>|  
|<span data-ttu-id="1090a-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="1090a-632">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-632">String</span></span>|  
|<span data-ttu-id="1090a-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1090a-634">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-634">Int16</span></span>|  
|<span data-ttu-id="1090a-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1090a-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1090a-636">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-636">String</span></span>|  
|<span data-ttu-id="1090a-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-637">DESCRIPTION</span></span>|<span data-ttu-id="1090a-638">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-638">String</span></span>|  
|<span data-ttu-id="1090a-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1090a-639">DATE_CREATED</span></span>|<span data-ttu-id="1090a-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-640">DateTime</span></span>|  
|<span data-ttu-id="1090a-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1090a-641">DATE_MODIFIED</span></span>|<span data-ttu-id="1090a-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1090a-643">Представления</span><span class="sxs-lookup"><span data-stu-id="1090a-643">Views</span></span>  
  
|<span data-ttu-id="1090a-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-644">ColumnName</span></span>|<span data-ttu-id="1090a-645">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-646">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-647">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-647">String</span></span>|  
|<span data-ttu-id="1090a-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-649">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-649">String</span></span>|  
|<span data-ttu-id="1090a-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-650">TABLE_NAME</span></span>|<span data-ttu-id="1090a-651">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-651">String</span></span>|  
|<span data-ttu-id="1090a-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1090a-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="1090a-653">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-653">String</span></span>|  
|<span data-ttu-id="1090a-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-654">CHECK_OPTION</span></span>|<span data-ttu-id="1090a-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-655">Boolean</span></span>|  
|<span data-ttu-id="1090a-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="1090a-656">IS_UPDATABLE</span></span>|<span data-ttu-id="1090a-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-657">Boolean</span></span>|  
|<span data-ttu-id="1090a-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1090a-658">DESCRIPTION</span></span>|<span data-ttu-id="1090a-659">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-659">String</span></span>|  
|<span data-ttu-id="1090a-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1090a-660">DATE_CREATED</span></span>|<span data-ttu-id="1090a-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-661">DateTime</span></span>|  
|<span data-ttu-id="1090a-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1090a-662">DATE_MODIFIED</span></span>|<span data-ttu-id="1090a-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="1090a-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1090a-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="1090a-664">Indexes</span></span>  
  
|<span data-ttu-id="1090a-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1090a-665">ColumnName</span></span>|<span data-ttu-id="1090a-666">DataType</span><span class="sxs-lookup"><span data-stu-id="1090a-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1090a-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-667">TABLE_CATALOG</span></span>|<span data-ttu-id="1090a-668">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-668">String</span></span>|  
|<span data-ttu-id="1090a-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="1090a-670">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-670">String</span></span>|  
|<span data-ttu-id="1090a-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-671">TABLE_NAME</span></span>|<span data-ttu-id="1090a-672">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-672">String</span></span>|  
|<span data-ttu-id="1090a-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1090a-673">INDEX_CATALOG</span></span>|<span data-ttu-id="1090a-674">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-674">String</span></span>|  
|<span data-ttu-id="1090a-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1090a-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="1090a-676">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-676">String</span></span>|  
|<span data-ttu-id="1090a-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-677">INDEX_NAME</span></span>|<span data-ttu-id="1090a-678">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-678">String</span></span>|  
|<span data-ttu-id="1090a-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1090a-679">PRIMARY_KEY</span></span>|<span data-ttu-id="1090a-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-680">Boolean</span></span>|  
|<span data-ttu-id="1090a-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1090a-681">UNIQUE</span></span>|<span data-ttu-id="1090a-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-682">Boolean</span></span>|  
|<span data-ttu-id="1090a-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1090a-683">CLUSTERED</span></span>|<span data-ttu-id="1090a-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-684">Boolean</span></span>|  
|<span data-ttu-id="1090a-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="1090a-685">TYPE</span></span>|<span data-ttu-id="1090a-686">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-686">Int32</span></span>|  
|<span data-ttu-id="1090a-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1090a-687">FILL_FACTOR</span></span>|<span data-ttu-id="1090a-688">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-688">Int32</span></span>|  
|<span data-ttu-id="1090a-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1090a-689">INITIAL_SIZE</span></span>|<span data-ttu-id="1090a-690">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-690">Int32</span></span>|  
|<span data-ttu-id="1090a-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="1090a-691">NULLS</span></span>|<span data-ttu-id="1090a-692">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-692">Int32</span></span>|  
|<span data-ttu-id="1090a-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1090a-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1090a-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-694">Boolean</span></span>|  
|<span data-ttu-id="1090a-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1090a-695">AUTO_UPDATE</span></span>|<span data-ttu-id="1090a-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-696">Boolean</span></span>|  
|<span data-ttu-id="1090a-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1090a-697">NULL_COLLATION</span></span>|<span data-ttu-id="1090a-698">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-698">Int32</span></span>|  
|<span data-ttu-id="1090a-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1090a-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="1090a-700">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-700">Int64</span></span>|  
|<span data-ttu-id="1090a-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1090a-701">COLUMN_NAME</span></span>|<span data-ttu-id="1090a-702">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-702">String</span></span>|  
|<span data-ttu-id="1090a-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1090a-703">COLUMN_GUID</span></span>|<span data-ttu-id="1090a-704">Guid</span><span class="sxs-lookup"><span data-stu-id="1090a-704">Guid</span></span>|  
|<span data-ttu-id="1090a-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1090a-705">COLUMN_PROPID</span></span>|<span data-ttu-id="1090a-706">Int64</span><span class="sxs-lookup"><span data-stu-id="1090a-706">Int64</span></span>|  
|<span data-ttu-id="1090a-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1090a-707">COLLATION</span></span>|<span data-ttu-id="1090a-708">Int16</span><span class="sxs-lookup"><span data-stu-id="1090a-708">Int16</span></span>|  
|<span data-ttu-id="1090a-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1090a-709">CARDINALITY</span></span>|<span data-ttu-id="1090a-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="1090a-710">Decimal</span></span>|  
|<span data-ttu-id="1090a-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="1090a-711">PAGES</span></span>|<span data-ttu-id="1090a-712">Int32</span><span class="sxs-lookup"><span data-stu-id="1090a-712">Int32</span></span>|  
|<span data-ttu-id="1090a-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1090a-713">FILTER_CONDITION</span></span>|<span data-ttu-id="1090a-714">Строковое</span><span class="sxs-lookup"><span data-stu-id="1090a-714">String</span></span>|  
|<span data-ttu-id="1090a-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1090a-715">INTEGRATED</span></span>|<span data-ttu-id="1090a-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="1090a-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1090a-717">См. также</span><span class="sxs-lookup"><span data-stu-id="1090a-717">See Also</span></span>  
 [<span data-ttu-id="1090a-718">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1090a-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

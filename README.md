USE [master]
GO
CREATE DATABASE [etimetracklite1] 
GO
USE [etimetracklite1]
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Visitors](
	[VisitorId] [int] IDENTITY(1,1) NOT NULL,
	[VisitorName] [nvarchar](255) NULL,
	[VisitorCompany] [nvarchar](255) NULL,
	[IsRegularVisitor] [int] NULL,
	[IsVIPVisitor] [int] NULL,
	[VisitorDesignation] [nvarchar](255) NULL,
	[VisitorLocation] [nvarchar](255) NULL,
	[VisitorAddress] [nvarchar](4000) NULL,
	[VisitorPhoneNo] [nvarchar](255) NULL,
	[VisitorMobileNo] [nvarchar](255) NULL,
	[VisitorEMail] [nvarchar](255) NULL,
	[VisitorType] [nvarchar](255) NULL,
	[VisitorRemarks] [nvarchar](255) NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [VISITOR_PK] PRIMARY KEY CLUSTERED 
(
	[VisitorId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[VisitorLogs]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[VisitorLogs](
	[VisitorLogId] [int] IDENTITY(1,1) NOT NULL,
	[VisitorId] [int] NULL,
	[EmployeeId] [int] NULL,
	[Purpose] [nvarchar](255) NULL,
	[VisitorIntime] [datetime] NULL,
	[VisitorOutTime] [datetime] NULL,
	[GateNo] [nvarchar](255) NULL,
	[IsAlone] [int] NULL,
	[VehicleType] [nvarchar](255) NULL,
	[VechileRegNo] [nvarchar](255) NULL,
	[VisitorLogRemarks] [nvarchar](4000) NULL,
	[VisitorStatus] [nvarchar](255) NULL,
	[IdCard] [nvarchar](255) NULL,
	[NoofPeople] [nvarchar](255) NULL,
	[BadgeValidity] [nvarchar](255) NULL,
	[MaterialCarried] [nvarchar](4000) NULL,
	[AccessCardId] [int] NULL,
 CONSTRAINT [VISITORLOG_PK] PRIMARY KEY CLUSTERED 
(
	[VisitorLogId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[VisitorFingerPrints]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[VisitorFingerPrints](
	[VisitorFingerPrintId] [int] IDENTITY(1,1) NOT NULL,
	[VisitorId] [int] NULL,
	[FPTemplate1] [nvarchar](4000) NULL,
	[FPTemplate2] [nvarchar](4000) NULL,
 CONSTRAINT [VISITORFINGERPRINT_PK] PRIMARY KEY CLUSTERED 
(
	[VisitorFingerPrintId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[VisitorFingerPrints] ON
INSERT [dbo].[VisitorFingerPrints] ([VisitorFingerPrintId], [VisitorId], [FPTemplate1], [FPTemplate2]) VALUES (1, 1, N'', N'')
SET IDENTITY_INSERT [dbo].[VisitorFingerPrints] OFF
/****** Object:  Table [dbo].[Vehicles]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Vehicles](
	[VehicleId] [int] IDENTITY(1,1) NOT NULL,
	[VehicleNumber] [nvarchar](255) NULL,
	[VehicleBrand] [nvarchar](255) NULL,
	[VehicleModel] [nvarchar](255) NULL,
	[VehicleEdition] [nvarchar](255) NULL,
	[VehicleOwnerName] [nvarchar](255) NULL,
	[VehicleOwnerPhoneNumber] [nvarchar](255) NULL,
	[VehicleType] [nvarchar](255) NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [VEHICLE_PK] PRIMARY KEY CLUSTERED 
(
	[VehicleId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[VehicleLogs]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[VehicleLogs](
	[VehicleLogId] [int] IDENTITY(1,1) NOT NULL,
	[VehicleId] [int] NULL,
	[ConcernPerson] [int] NULL,
	[PurposeOfEntry] [nvarchar](255) NULL,
	[VehicleInTime] [datetime] NULL,
	[VehicleOutTime] [datetime] NULL,
	[GateNumber] [nvarchar](255) NULL,
	[MaterialCarriedInside] [nvarchar](4000) NULL,
	[Status] [nvarchar](255) NULL,
	[BadgeValidity] [nvarchar](255) NULL,
	[BadgeRemarks] [nvarchar](255) NULL,
 CONSTRAINT [VEHICLELOG_PK] PRIMARY KEY CLUSTERED 
(
	[VehicleLogId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[UsersFP]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[UsersFP](
	[UsersFPId] [int] IDENTITY(1,1) NOT NULL,
	[UserPin] [nvarchar](50) NULL,
	[Privilege] [nvarchar](50) NULL,
	[FID] [int] NULL,
	[FingerPrint] [ntext] NULL,
 CONSTRAINT [PK_UsersFP] PRIMARY KEY CLUSTERED 
(
	[UsersFPId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Users]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Users](
	[UserId] [int] IDENTITY(1,1) NOT NULL,
	[LoginName] [nvarchar](50) NOT NULL,
	[LoginPassword] [nvarchar](50) NULL,
	[RoleName] [nvarchar](255) NULL,
	[IsAdmin] [int] NOT NULL,
	[AccessI] [int] NOT NULL,
	[RecordStatus] [int] NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
 CONSTRAINT [PK_Users] PRIMARY KEY CLUSTERED 
(
	[UserId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[Users] ON
INSERT [dbo].[Users] ([UserId], [LoginName], [LoginPassword], [RoleName], [IsAdmin], [AccessI], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7]) VALUES (110, N'essl', N'79195F54068C15E0DC4AAFDC97740DFC', N'Admin', -1, 1, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL)
SET IDENTITY_INSERT [dbo].[Users] OFF
/****** Object:  Table [dbo].[UserPermissions]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[UserPermissions](
	[UserPermissionId] [int] IDENTITY(1,1) NOT NULL,
	[UserId] [int] NOT NULL,
	[PermissionId] [int] NOT NULL,
 CONSTRAINT [PK_UserPermissions] PRIMARY KEY CLUSTERED 
(
	[UserPermissionId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[UserCompanies]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[UserCompanies](
	[UserCompanyId] [int] IDENTITY(1,1) NOT NULL,
	[UserId] [int] NOT NULL,
	[CompanyId] [int] NOT NULL,
 CONSTRAINT [PK_UserCompanies] PRIMARY KEY CLUSTERED 
(
	[UserCompanyId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[TimeZones]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[TimeZones](
	[TimeZoneId] [int] IDENTITY(1,1) NOT NULL,
	[TimeZoneName] [nvarchar](255) NULL,
	[Description] [nvarchar](255) NULL,
	[SundayTiming] [nvarchar](255) NULL,
	[MondayTiming] [nvarchar](255) NULL,
	[TuesdayTiming] [nvarchar](255) NULL,
	[WednesdayTiming] [nvarchar](255) NULL,
	[ThursdayTiming] [nvarchar](255) NULL,
	[FridayTiming] [nvarchar](255) NULL,
	[SaturdayTiming] [nvarchar](255) NULL,
	[HolidayType1Timing] [nvarchar](255) NULL,
	[HolidayType2Timing] [nvarchar](255) NULL,
	[HolidayType3Timing] [nvarchar](255) NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [TimeZones_PK] PRIMARY KEY CLUSTERED 
(
	[TimeZoneId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[TimeZones] ON
INSERT [dbo].[TimeZones] ([TimeZoneId], [TimeZoneName], [Description], [SundayTiming], [MondayTiming], [TuesdayTiming], [WednesdayTiming], [ThursdayTiming], [FridayTiming], [SaturdayTiming], [HolidayType1Timing], [HolidayType2Timing], [HolidayType3Timing], [RecordStatus]) VALUES (1, N'Accessible 24 Hours', N'', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', N'    00:00;    23:59;    00:00;    00:00;    00:00;    00:00;', 1)
SET IDENTITY_INSERT [dbo].[TimeZones] OFF
/****** Object:  Table [dbo].[SpecialEntries]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[SpecialEntries](
	[SpecialEntryId] [int] IDENTITY(1,1) NOT NULL,
	[SpecialType] [nvarchar](255) NOT NULL,
	[EmployeeId] [int] NOT NULL,
	[SpecialEntryStatus] [nvarchar](255) NULL,
	[Duration] [int] NOT NULL,
	[FromDate] [datetime] NOT NULL,
	[ToDate] [datetime] NOT NULL,
	[BeginTime] [nvarchar](255) NULL,
	[EndTime] [nvarchar](255) NULL,
	[IsApproved] [int] NOT NULL,
	[ApprovedBy] [nvarchar](255) NULL,
	[Remarks] [nvarchar](4000) NULL,
	[BeginTime2] [nvarchar](255) NULL,
	[EndTime2] [nvarchar](255) NULL,
	[LastModifiedBy] [nvarchar](50) NULL,
 CONSTRAINT [PK_SpecialEntries] PRIMARY KEY CLUSTERED 
(
	[SpecialEntryId] ASC,
	[EmployeeId] ASC,
	[FromDate] ASC,
	[ToDate] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Shifts]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Shifts](
	[ShiftId] [int] IDENTITY(1,1) NOT NULL,
	[ShiftFName] [nvarchar](50) NOT NULL,
	[ShiftSName] [nvarchar](50) NOT NULL,
	[BeginTime] [nvarchar](50) NULL,
	[EndTime] [nvarchar](50) NULL,
	[Break1] [int] NULL,
	[Break2] [int] NULL,
	[Break1BeginTime] [nvarchar](50) NULL,
	[Break2BeginTime] [nvarchar](50) NULL,
	[Break1EndTime] [nvarchar](50) NULL,
	[Break2EndTime] [nvarchar](50) NULL,
	[ShiftDuration] [int] NOT NULL,
	[Break1Duration] [int] NOT NULL,
	[Break2Duration] [int] NOT NULL,
	[ShiftType] [nvarchar](50) NOT NULL,
	[RecordStatus] [int] NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
	[PunchBeginDuration] [int] NULL,
	[PunchEndDuration] [int] NULL,
	[IsGraceTimeApplicable] [int] NULL,
	[GraceTime] [nvarchar](255) NULL,
	[IsPartialDayApplicable] [int] NULL,
	[PartialDay] [nvarchar](255) NULL,
	[PartialDayBeginTime] [nvarchar](255) NULL,
	[PartialDayEndTime] [nvarchar](255) NULL,
 CONSTRAINT [PK_Shifts] PRIMARY KEY CLUSTERED 
(
	[ShiftId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[Shifts] ON
INSERT [dbo].[Shifts] ([ShiftId], [ShiftFName], [ShiftSName], [BeginTime], [EndTime], [Break1], [Break2], [Break1BeginTime], [Break2BeginTime], [Break1EndTime], [Break2EndTime], [ShiftDuration], [Break1Duration], [Break2Duration], [ShiftType], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [PunchBeginDuration], [PunchEndDuration], [IsGraceTimeApplicable], [GraceTime], [IsPartialDayApplicable], [PartialDay], [PartialDayBeginTime], [PartialDayEndTime]) VALUES (1, N'Weekly Off', N'WO', N'00:00', N'00:00', 0, 0, NULL, NULL, NULL, NULL, 0, 0, 0, N'Shift', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 0, 0, 0, N'', 0, N'', N'', N'')
INSERT [dbo].[Shifts] ([ShiftId], [ShiftFName], [ShiftSName], [BeginTime], [EndTime], [Break1], [Break2], [Break1BeginTime], [Break2BeginTime], [Break1EndTime], [Break2EndTime], [ShiftDuration], [Break1Duration], [Break2Duration], [ShiftType], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [PunchBeginDuration], [PunchEndDuration], [IsGraceTimeApplicable], [GraceTime], [IsPartialDayApplicable], [PartialDay], [PartialDayBeginTime], [PartialDayEndTime]) VALUES (2, N'Fixed Shift', N'FS', N'09:00', N'18:30', 0, 0, N' ', N' ', N' ', N' ', 0, 0, 0, N'Shift', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 0, 0, 0, N'', 0, N'', N'', N'')
INSERT [dbo].[Shifts] ([ShiftId], [ShiftFName], [ShiftSName], [BeginTime], [EndTime], [Break1], [Break2], [Break1BeginTime], [Break2BeginTime], [Break1EndTime], [Break2EndTime], [ShiftDuration], [Break1Duration], [Break2Duration], [ShiftType], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [PunchBeginDuration], [PunchEndDuration], [IsGraceTimeApplicable], [GraceTime], [IsPartialDayApplicable], [PartialDay], [PartialDayBeginTime], [PartialDayEndTime]) VALUES (3, N'NoShift', N'NS', N'00:00', N'00:00', 0, 0, NULL, N' ', NULL, N' ', 0, 0, 0, N'Shift', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 0, 0, 0, N'', 0, N'', N'', N'')
INSERT [dbo].[Shifts] ([ShiftId], [ShiftFName], [ShiftSName], [BeginTime], [EndTime], [Break1], [Break2], [Break1BeginTime], [Break2BeginTime], [Break1EndTime], [Break2EndTime], [ShiftDuration], [Break1Duration], [Break2Duration], [ShiftType], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [PunchBeginDuration], [PunchEndDuration], [IsGraceTimeApplicable], [GraceTime], [IsPartialDayApplicable], [PartialDay], [PartialDayBeginTime], [PartialDayEndTime]) VALUES (4, N'Holiday', N'H', N'00:00', N'00:00', 0, 0, NULL, NULL, NULL, NULL, 0, 0, 0, N'Shift', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 0, 0, 0, N'', 0, N'', N'', N'')
INSERT [dbo].[Shifts] ([ShiftId], [ShiftFName], [ShiftSName], [BeginTime], [EndTime], [Break1], [Break2], [Break1BeginTime], [Break2BeginTime], [Break1EndTime], [Break2EndTime], [ShiftDuration], [Break1Duration], [Break2Duration], [ShiftType], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [PunchBeginDuration], [PunchEndDuration], [IsGraceTimeApplicable], [GraceTime], [IsPartialDayApplicable], [PartialDay], [PartialDayBeginTime], [PartialDayEndTime]) VALUES (5, N'General', N'GS', N'09:30', N'18:30', 0, 0, N'21:34', N'21:34', N'21:34', N'21:34', 540, 0, 0, N'Shift', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 0, 0, 0, N'', 0, N'', N'', N'')
INSERT [dbo].[Shifts] ([ShiftId], [ShiftFName], [ShiftSName], [BeginTime], [EndTime], [Break1], [Break2], [Break1BeginTime], [Break2BeginTime], [Break1EndTime], [Break2EndTime], [ShiftDuration], [Break1Duration], [Break2Duration], [ShiftType], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [PunchBeginDuration], [PunchEndDuration], [IsGraceTimeApplicable], [GraceTime], [IsPartialDayApplicable], [PartialDay], [PartialDayBeginTime], [PartialDayEndTime]) VALUES (8, N'Sample Calendar', N'Sam', N'00:00', N'00:00', 0, 0, NULL, NULL, NULL, NULL, 0, 0, 0, N'ShiftCalendar', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 0, 0, 0, N'', 0, N'', N'', N'')
SET IDENTITY_INSERT [dbo].[Shifts] OFF
/****** Object:  Table [dbo].[ShiftRotationMasterShifts]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ShiftRotationMasterShifts](
	[ShiftRotationMasterShiftId] [int] IDENTITY(1,1) NOT NULL,
	[ShiftDate] [datetime] NULL,
	[ShiftId] [int] NULL,
	[ShiftRotationMasterId] [int] NULL,
 CONSTRAINT [ShiftRotationMasterShifts_PK] PRIMARY KEY CLUSTERED 
(
	[ShiftRotationMasterShiftId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ShiftRotationMasters]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ShiftRotationMasters](
	[ShiftRotationMasterId] [int] IDENTITY(1,1) NOT NULL,
	[ShiftRotationMasterName] [nvarchar](50) NULL,
	[BeginDay] [datetime] NULL,
	[EndDay] [datetime] NULL,
	[SHIFTROTATIONTYPE] [nvarchar](50) NULL,
	[Day1] [nvarchar](50) NULL,
	[ShiftId1] [int] NULL,
	[Day2] [nvarchar](50) NULL,
	[ShiftId2] [int] NULL,
	[Day3] [nvarchar](50) NULL,
	[ShiftId3] [int] NULL,
	[Day4] [nvarchar](50) NULL,
	[ShiftId4] [int] NULL,
	[Day5] [nvarchar](50) NULL,
	[ShiftId5] [int] NULL,
	[Day6] [nvarchar](50) NULL,
	[ShiftId6] [int] NULL,
	[Day7] [nvarchar](50) NULL,
	[ShiftId7] [int] NULL,
	[Day8] [nvarchar](50) NULL,
	[ShiftId8] [int] NULL,
	[Day9] [nvarchar](50) NULL,
	[ShiftId9] [int] NULL,
	[Day10] [nvarchar](50) NULL,
	[ShiftId10] [int] NULL,
	[Day11] [nvarchar](50) NULL,
	[ShiftId11] [int] NULL,
	[Day12] [nvarchar](50) NULL,
	[ShiftId12] [int] NULL,
	[Day13] [nvarchar](50) NULL,
	[ShiftId13] [int] NULL,
	[Day14] [nvarchar](50) NULL,
	[ShiftId14] [int] NULL,
	[Day15] [nvarchar](50) NULL,
	[ShiftId15] [int] NULL,
	[Day16] [nvarchar](50) NULL,
	[ShiftId16] [int] NULL,
	[Day17] [nvarchar](50) NULL,
	[ShiftId17] [int] NULL,
	[Day18] [nvarchar](50) NULL,
	[ShiftId18] [int] NULL,
	[Day19] [nvarchar](50) NULL,
	[ShiftId19] [int] NULL,
	[Day20] [nvarchar](50) NULL,
	[ShiftId20] [int] NULL,
	[Day21] [nvarchar](50) NULL,
	[ShiftId21] [int] NULL,
	[Day22] [nvarchar](50) NULL,
	[ShiftId22] [int] NULL,
	[Day23] [nvarchar](50) NULL,
	[ShiftId23] [int] NULL,
	[Day24] [nvarchar](50) NULL,
	[ShiftId24] [int] NULL,
	[Day25] [nvarchar](50) NULL,
	[ShiftId25] [int] NULL,
	[Day26] [nvarchar](50) NULL,
	[ShiftId26] [int] NULL,
	[Day27] [nvarchar](50) NULL,
	[ShiftId27] [int] NULL,
	[Day28] [nvarchar](50) NULL,
	[ShiftId28] [int] NULL,
	[Day29] [nvarchar](50) NULL,
	[ShiftId29] [int] NULL,
	[Day30] [nvarchar](50) NULL,
	[ShiftId30] [int] NULL,
	[Day31] [nvarchar](50) NULL,
	[ShiftId31] [int] NULL,
	[SundayWeeklyOff] [int] NULL,
	[SaturdayWeeklyOff] [int] NULL,
	[WeeklyOff1] [nvarchar](50) NULL,
	[WeeklyOff2] [nvarchar](50) NULL,
	[WhichSaturday] [nvarchar](50) NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [ShiftRotationMasters_PK] PRIMARY KEY CLUSTERED 
(
	[ShiftRotationMasterId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ShiftGroupShifts]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ShiftGroupShifts](
	[ShiftGroupShiftId] [int] IDENTITY(1,1) NOT NULL,
	[ShiftGroupId] [int] NULL,
	[ShiftId] [int] NULL,
 CONSTRAINT [ShiftGroupShifts_PK] PRIMARY KEY CLUSTERED 
(
	[ShiftGroupShiftId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ShiftGroups]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ShiftGroups](
	[ShiftGroupId] [int] IDENTITY(1,1) NOT NULL,
	[ShiftGroupFName] [nvarchar](255) NULL,
	[ShiftGroupSName] [nvarchar](255) NULL,
 CONSTRAINT [ShiftGroups_PK] PRIMARY KEY CLUSTERED 
(
	[ShiftGroupId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ShiftCalendarShifts]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ShiftCalendarShifts](
	[ShiftCalendarShiftId] [int] IDENTITY(1,1) NOT NULL,
	[ShiftCalendarId] [int] NOT NULL,
	[ShiftId] [int] NOT NULL,
	[ShiftDate] [smalldatetime] NOT NULL,
 CONSTRAINT [PK_ShiftCalendarShifts] PRIMARY KEY CLUSTERED 
(
	[ShiftCalendarShiftId] ASC,
	[ShiftCalendarId] ASC,
	[ShiftDate] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[SalaryStructures]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[SalaryStructures](
	[SalaryStructureid] [int] IDENTITY(1,1) NOT NULL,
	[EffectiveDate] [datetime] NULL,
	[EmployeeId] [int] NULL,
	[Basic] [nvarchar](255) NULL,
	[HRA] [nvarchar](255) NULL,
	[DA] [nvarchar](255) NULL,
	[Conveyance] [nvarchar](255) NULL,
	[TDSApplicable] [int] NULL,
	[TDS] [nvarchar](255) NULL,
	[ESICApplicable] [int] NULL,
	[ESIC] [nvarchar](255) NULL,
	[ESICEmployerContribution] [nvarchar](255) NULL,
	[PFApplicable] [int] NULL,
	[PF] [nvarchar](255) NULL,
	[PFEmployerContribution] [nvarchar](255) NULL,
	[PTApplicable] [int] NULL,
	[PT] [nvarchar](255) NULL,
	[OTApplicable] [int] NULL,
	[OTPerhour] [nvarchar](255) NULL,
	[LOPApplicable] [int] NULL,
	[LOP] [nvarchar](255) NULL,
	[IsLOPFixed] [int] NULL,
	[IsPFFloating] [int] NULL,
	[IsESICFloating] [int] NULL,
	[IsPTFloating] [int] NULL,
 CONSTRAINT [SalaryStructures_Pk] PRIMARY KEY CLUSTERED 
(
	[SalaryStructureid] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[SalaryStructureEarnings]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[SalaryStructureEarnings](
	[SalaryStructureEarningId] [int] IDENTITY(1,1) NOT NULL,
	[SalaryStructureId] [int] NULL,
	[EarningType] [nvarchar](255) NULL,
	[Amount] [nvarchar](255) NULL,
	[Remarks] [nvarchar](4000) NULL,
	[IsTaxable] [int] NULL,
 CONSTRAINT [SalaryStructureEarnings_Pk] PRIMARY KEY CLUSTERED 
(
	[SalaryStructureEarningId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[SalaryStructureDeductions]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[SalaryStructureDeductions](
	[SalaryStructureDeductionId] [int] IDENTITY(1,1) NOT NULL,
	[SalaryStructureId] [int] NULL,
	[DeductionType] [nvarchar](255) NULL,
	[Amount] [nvarchar](255) NULL,
	[Remarks] [nvarchar](4000) NULL,
	[IsTaxable] [int] NULL,
 CONSTRAINT [SalaryStructureDeductions_Pk] PRIMARY KEY CLUSTERED 
(
	[SalaryStructureDeductionId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ReportCustom]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ReportCustom](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[ReportName] [nvarchar](255) NOT NULL,
	[ReportFieldValueName] [nvarchar](255) NOT NULL,
	[ReportFieldDisplayName] [nvarchar](255) NOT NULL,
	[FieldOrder] [int] NOT NULL,
 CONSTRAINT [PK_ReportCustom] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Reimbursements]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Reimbursements](
	[ReimbursementId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeId] [int] NULL,
	[ReimbursementDate] [datetime] NULL,
	[ReimbursementReason] [nvarchar](255) NULL,
	[IsApproved] [int] NULL,
	[ReimbursementAmount] [nvarchar](255) NULL,
	[Remarks] [nvarchar](4000) NULL,
 CONSTRAINT [Reimbursements_Pk] PRIMARY KEY CLUSTERED 
(
	[ReimbursementId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[PunchTimeDetails]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[PunchTimeDetails](
	[PunchTimeDetailsId] [int] IDENTITY(1,1) NOT NULL,
	[tktno] [nvarchar](255) NULL,
	[hhmm] [float] NULL,
	[tmmm] [float] NULL,
	[hh_mm] [float] NULL,
	[flag] [nvarchar](255) NULL,
	[date] [datetime] NULL,
	[sno] [float] NULL,
	[INOUT] [nvarchar](255) NULL,
 CONSTRAINT [PunchTimeDetails_Pk] PRIMARY KEY CLUSTERED 
(
	[PunchTimeDetailsId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Permissions]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Permissions](
	[PermissionId] [int] NOT NULL,
	[Permission] [nvarchar](255) NULL,
PRIMARY KEY CLUSTERED 
(
	[PermissionId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (1, N'Users')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (2, N'ViewUsers')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (3, N'AddUsers')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (4, N'EditUsers')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (5, N'DeleteUsers')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (6, N'MasterSettings')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (7, N'MailSettings')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (8, N'Companies')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (9, N'ViewCompanies')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (10, N'AddCompanies')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (11, N'EditCompanies')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (12, N'DeleteCompanies')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (13, N'Departments')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (14, N'ViewDepartments')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (15, N'AddDepartments')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (16, N'EditDepartments')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (17, N'DeleteDepartments')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (18, N'EmpCategories')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (19, N'ViewEmpCategories')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (20, N'AddEmpCategories')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (21, N'EditEmpCategories')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (22, N'DeleteEmpCategories')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (23, N'Shifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (24, N'ViewShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (25, N'AddShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (26, N'EditShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (27, N'DeleteShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (28, N'ShiftCalendars')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (29, N'ViewShiftCalendars')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (30, N'AddShiftCalendars')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (31, N'EditShiftCalendars')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (32, N'DeleteShiftCalendars')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (33, N'Holidays')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (34, N'ViewHolidays')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (35, N'AddHolidays')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (36, N'EditHolidays')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (37, N'DeleteHolidays')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (38, N'Employees')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (39, N'ViewEmployees')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (40, N'AddEmployees')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (41, N'EditEmployees')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (42, N'DeleteEmployees')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (43, N'LeaveTypes')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (44, N'ViewLeaveTypes')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (45, N'AddLeaveTypes')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (46, N'EditLeaveTypes')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (47, N'DeleteLeaveTypes')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (48, N'DepartmentShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (49, N'ViewDepartmentShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (50, N'AddDepartmentShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (51, N'EditDepartmentShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (52, N'DeleteDepartmentShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (53, N'EmployeeShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (54, N'ViewEmployeeShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (55, N'AddEmployeeShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (56, N'EditEmployeeShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (57, N'DeleteEmployeeShifts')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (58, N'LeaveEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (59, N'ViewLeaveEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (60, N'AddLeaveEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (61, N'EditLeaveEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (62, N'DeleteLeaveEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (63, N'OutDoorEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (64, N'ViewOutDoorEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (65, N'AddOutDoorEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (66, N'EditOutDoorEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (67, N'DeleteOutDoorEntries')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (68, N'LogRecords')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (69, N'ViewLogRecords')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (70, N'AddLogRecords')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (71, N'EditLogRecords')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (72, N'DeleteLogRecords')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (73, N'OTRegister')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (74, N'LeaveSummary')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (75, N'AttendanceLogs')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (76, N'DeviceManagement')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (77, N'ImportEmployees')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (78, N'ExportEmployees')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (79, N'BackUpDatabase')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (80, N'BackupRestoreOldLogs')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (81, N'AttendanceRegister')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (82, N'GenerateReports')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (83, N'OnlineDownloader')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (84, N'VisitorManagement')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (85, N'ManageWorkCode')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (86, N'ManageCanteen')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (87, N'PayrollManagement')
INSERT [dbo].[Permissions] ([PermissionId], [Permission]) VALUES (88, N'AboutUs')
/****** Object:  Table [dbo].[PayslipRecords]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[PayslipRecords](
	[PayslipRecordId] [int] IDENTITY(1,1) NOT NULL,
	[PayslipDate] [datetime] NULL,
	[EmployeeId] [int] NULL,
	[Basic] [nvarchar](255) NULL,
	[HRA] [nvarchar](255) NULL,
	[DA] [nvarchar](255) NULL,
	[Conveyance] [nvarchar](255) NULL,
	[TDS] [nvarchar](255) NULL,
	[ESIC] [nvarchar](255) NULL,
	[PF] [nvarchar](255) NULL,
	[PT] [nvarchar](255) NULL,
	[OTHours] [nvarchar](255) NULL,
	[OTPerHour] [nvarchar](255) NULL,
	[TotalOT] [nvarchar](255) NULL,
	[LOPPerDay] [nvarchar](255) NULL,
	[AbsentDays] [nvarchar](255) NULL,
	[LWOPDays] [nvarchar](255) NULL,
	[TotalLOP] [nvarchar](255) NULL,
	[IsFreezed] [int] NULL,
	[ESICEmployerContribution] [nvarchar](255) NULL,
	[PFEmployerContribution] [nvarchar](255) NULL,
 CONSTRAINT [PayslipRecords_Pk] PRIMARY KEY CLUSTERED 
(
	[PayslipRecordId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[PayslipEarnings]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[PayslipEarnings](
	[PayslipEarningId] [int] IDENTITY(1,1) NOT NULL,
	[PayslipRecordId] [int] NULL,
	[EarningType] [nvarchar](255) NULL,
	[Amount] [nvarchar](255) NULL,
	[Remarks] [nvarchar](4000) NULL,
	[IsTaxable] [int] NULL,
 CONSTRAINT [PayslipEarnings_Pk] PRIMARY KEY CLUSTERED 
(
	[PayslipEarningId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[PayslipDeductions]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[PayslipDeductions](
	[PayslipDeductionId] [int] IDENTITY(1,1) NOT NULL,
	[PayslipRecordId] [int] NULL,
	[DeductionType] [nvarchar](255) NULL,
	[Amount] [nvarchar](255) NULL,
	[Remarks] [nvarchar](4000) NULL,
	[IsTaxable] [int] NULL,
 CONSTRAINT [PayslipDeductions_Pk] PRIMARY KEY CLUSTERED 
(
	[PayslipDeductionId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[PayrollFormulas]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[PayrollFormulas](
	[PayrollFormulaId] [int] IDENTITY(1,1) NOT NULL,
	[FormulaName] [nvarchar](2000) NULL,
	[FormulaValue] [nvarchar](2000) NULL,
 CONSTRAINT [PayrollFormula_PK] PRIMARY KEY CLUSTERED 
(
	[PayrollFormulaId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ParallelDatabaseDetails]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ParallelDatabaseDetails](
	[IsParallelDatabaseDowload] [int] NULL,
	[DatabaseType] [nvarchar](255) NULL,
	[Service] [nvarchar](255) NULL,
	[Port] [nvarchar](255) NULL,
	[ServerName] [nvarchar](255) NULL,
	[DatabaseName] [nvarchar](255) NULL,
	[DatabaseUserName] [nvarchar](255) NULL,
	[DatabasePassword] [nvarchar](255) NULL,
	[TableName] [nvarchar](255) NULL,
	[EmployeeCode] [nvarchar](255) NULL,
	[LogDate] [nvarchar](255) NULL,
	[Direction] [nvarchar](255) NULL,
	[WorkCode] [nvarchar](255) NULL,
	[IsReservedField1] [int] NULL,
	[IsReservedField2] [int] NULL,
	[ReservedField1] [nvarchar](255) NULL,
	[ReservedField1Value] [nvarchar](255) NULL,
	[ReservedField2] [nvarchar](255) NULL,
	[ReservedField2Value] [nvarchar](255) NULL,
	[LogTime] [nvarchar](255) NULL,
	[LogDateTime] [nvarchar](255) NULL,
	[LogTimeFormat] [nvarchar](255) NULL,
	[LogDateTimeFormat] [nvarchar](255) NULL,
	[LogDateFormat] [nvarchar](255) NULL,
	[InValue] [nvarchar](255) NULL,
	[OutValue] [nvarchar](255) NULL
) ON [PRIMARY]
GO
INSERT [dbo].[ParallelDatabaseDetails] ([IsParallelDatabaseDowload], [DatabaseType], [Service], [Port], [ServerName], [DatabaseName], [DatabaseUserName], [DatabasePassword], [TableName], [EmployeeCode], [LogDate], [Direction], [WorkCode], [IsReservedField1], [IsReservedField2], [ReservedField1], [ReservedField1Value], [ReservedField2], [ReservedField2Value], [LogTime], [LogDateTime], [LogTimeFormat], [LogDateTimeFormat], [LogDateFormat], [InValue], [OutValue]) VALUES (0, N'MS SQL Server', N'', N'', N'localhost', N'TimeTrack', N'', N'', N'AttendanceLogs', N'EmployeeCode', N'LogDate', N'Direction', N'WorkCode', 0, 0, N'', N'', N'', N'', N'LogTime', N'LogDateTime', N'yyyy-MM-dd HH:mm:ss', N'yyyy-MM-dd HH:mm:ss', N'yyyy-MM-dd HH:mm:ss', N'in', N'out')
/****** Object:  Table [dbo].[ParallelAttLogExportDetails]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ParallelAttLogExportDetails](
	[IsParallelDatabaseDowload] [int] NULL,
	[DatabaseType] [nvarchar](255) NULL,
	[Service] [nvarchar](255) NULL,
	[Port] [nvarchar](255) NULL,
	[ServerName] [nvarchar](255) NULL,
	[DatabaseName] [nvarchar](255) NULL,
	[DatabaseUserName] [nvarchar](255) NULL,
	[DatabasePassword] [nvarchar](255) NULL,
	[TableName] [nvarchar](255) NULL,
	[DBPath] [nvarchar](255) NULL,
	[AttendanceDate] [nvarchar](255) NULL,
	[AttendanceDateFormat] [nvarchar](255) NULL,
	[EmployeeCode] [nvarchar](255) NULL,
	[Company] [nvarchar](255) NULL,
	[Category] [nvarchar](255) NULL,
	[Department] [nvarchar](255) NULL,
	[Designation] [nvarchar](255) NULL,
	[EmployementType] [nvarchar](255) NULL,
	[InDate] [nvarchar](255) NULL,
	[InDateFormat] [nvarchar](255) NULL,
	[InTime] [nvarchar](255) NULL,
	[InTimeFormat] [nvarchar](255) NULL,
	[InDevice] [nvarchar](255) NULL,
	[InLocation] [nvarchar](255) NULL,
	[OutDate] [nvarchar](255) NULL,
	[OutDateFormat] [nvarchar](255) NULL,
	[OutTime] [nvarchar](255) NULL,
	[OutTimeFormat] [nvarchar](255) NULL,
	[OutDevice] [nvarchar](255) NULL,
	[OutLocation] [nvarchar](255) NULL,
	[Status] [nvarchar](255) NULL,
	[StatusCode] [nvarchar](255) NULL,
	[Duration] [nvarchar](255) NULL,
	[LateBy] [nvarchar](255) NULL,
	[EarlyBy] [nvarchar](255) NULL,
	[OverTime] [nvarchar](255) NULL,
	[IsOnLeave] [nvarchar](255) NULL,
	[LeaveType] [nvarchar](255) NULL,
	[IsOnOD] [nvarchar](255) NULL,
	[ODDuration] [nvarchar](255) NULL,
	[PunchRecords] [nvarchar](255) NULL,
	[ShiftName] [nvarchar](255) NULL,
	[IsReservedField1] [int] NULL,
	[IsReservedField2] [int] NULL,
	[IsReservedField3] [int] NULL,
	[ReservedField1] [nvarchar](255) NULL,
	[ReservedField1Value] [nvarchar](255) NULL,
	[ReservedField2] [nvarchar](255) NULL,
	[ReservedField2Value] [nvarchar](255) NULL,
	[ReservedField3] [nvarchar](255) NULL,
	[ReservedField3Value] [nvarchar](255) NULL
) ON [PRIMARY]
GO
INSERT [dbo].[ParallelAttLogExportDetails] ([IsParallelDatabaseDowload], [DatabaseType], [Service], [Port], [ServerName], [DatabaseName], [DatabaseUserName], [DatabasePassword], [TableName], [DBPath], [AttendanceDate], [AttendanceDateFormat], [EmployeeCode], [Company], [Category], [Department], [Designation], [EmployementType], [InDate], [InDateFormat], [InTime], [InTimeFormat], [InDevice], [InLocation], [OutDate], [OutDateFormat], [OutTime], [OutTimeFormat], [OutDevice], [OutLocation], [Status], [StatusCode], [Duration], [LateBy], [EarlyBy], [OverTime], [IsOnLeave], [LeaveType], [IsOnOD], [ODDuration], [PunchRecords], [ShiftName], [IsReservedField1], [IsReservedField2], [IsReservedField3], [ReservedField1], [ReservedField1Value], [ReservedField2], [ReservedField2Value], [ReservedField3], [ReservedField3Value]) VALUES (0, N'Oracle', N'XE', N'1521', N'Localhost', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', N' ', 0, 0, 0, N' ', N' ', N' ', N' ', N' ', N' ')
/****** Object:  Table [dbo].[MultiGroups]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[MultiGroups](
	[MultiGroupId] [int] IDENTITY(1,1) NOT NULL,
	[MultiGroupName] [nvarchar](255) NULL,
	[Description] [nvarchar](255) NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [MultiGroups_PK] PRIMARY KEY CLUSTERED 
(
	[MultiGroupId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[MultiGroupMembers]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[MultiGroupMembers](
	[MultiGroupMemberId] [int] IDENTITY(1,1) NOT NULL,
	[MultigroupId] [int] NULL,
	[EmployeeId] [int] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [MultiGroupMembers_PK] PRIMARY KEY CLUSTERED 
(
	[MultiGroupMemberId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[MultiCardCombinations]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[MultiCardCombinations](
	[MultiCardCombinationId] [int] IDENTITY(1,1) NOT NULL,
	[MultiCardCombinationName] [nvarchar](255) NULL,
	[ControllerId] [int] NULL,
	[DoorId] [int] NULL,
	[Group1] [int] NULL,
	[Group2] [int] NULL,
	[Group3] [int] NULL,
	[Group4] [int] NULL,
	[Group5] [int] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [MultiCardCombinations_PK] PRIMARY KEY CLUSTERED 
(
	[MultiCardCombinationId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[MasterSettings]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[MasterSettings](
	[MasterDetailsId] [int] IDENTITY(1,1) NOT NULL,
	[IsAlphaNumericEmployeeCode] [int] NOT NULL,
	[IsFixedShift] [int] NOT NULL,
	[ShiftBeginTime] [nvarchar](255) NULL,
	[ShiftEndTime] [nvarchar](255) NULL,
	[IsDeviceCodeSame] [int] NOT NULL,
	[AttendanceYearStartMonth] [nvarchar](255) NULL,
	[AttendanceYearStartDate] [nvarchar](255) NULL,
	[ExtraHourShiftExpires] [int] NULL,
	[LiecenceKey] [nvarchar](255) NULL,
	[PunchBeginDuration] [int] NULL,
	[Version] [nvarchar](50) NULL,
	[IsAutoBackUp] [int] NOT NULL,
	[AutoBackuppath] [nvarchar](255) NULL,
	[BackupDays] [int] NULL,
	[LastBackUpDate] [nvarchar](50) NULL,
	[MinDiffBetweenTwoPunch] [int] NULL,
	[IsAutoShift] [int] NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
	[C8] [nvarchar](255) NULL,
	[C9] [nvarchar](255) NULL,
	[C10] [nvarchar](255) NULL,
	[C11] [nvarchar](255) NULL,
	[C12] [nvarchar](255) NULL,
	[C13] [nvarchar](255) NULL,
	[C14] [nvarchar](255) NULL,
	[C15] [nvarchar](255) NULL,
	[MemoLateEarlySubject] [nvarchar](4000) NULL,
	[MemoMissedPunchSubject] [nvarchar](4000) NULL,
	[MemoSignature] [nvarchar](4000) NULL,
	[MemoAbsentText] [nvarchar](4000) NULL,
	[MemoLateEarlyText] [nvarchar](4000) NULL,
	[MemoMissedPunchText] [nvarchar](4000) NULL,
	[MemoAbsentSubject] [nvarchar](2000) NULL,
	[EmployeePhotoPath] [nvarchar](255) NULL,
	[VisitorPhotoPath] [nvarchar](255) NULL,
	[VisitorFingerPrintPath] [nvarchar](255) NULL,
	[VehiclePhotoPath] [nvarchar](255) NULL,
	[IsAutoClearLogs] [int] NULL,
	[MemoHalfDayForLateEarlySubject] [nvarchar](4000) NULL,
	[MemoHalfDayForLateEarlyText] [nvarchar](4000) NULL,
 CONSTRAINT [PK_MasterSettings] PRIMARY KEY CLUSTERED 
(
	[MasterDetailsId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[MasterSettings] ON
INSERT [dbo].[MasterSettings] ([MasterDetailsId], [IsAlphaNumericEmployeeCode], [IsFixedShift], [ShiftBeginTime], [ShiftEndTime], [IsDeviceCodeSame], [AttendanceYearStartMonth], [AttendanceYearStartDate], [ExtraHourShiftExpires], [LiecenceKey], [PunchBeginDuration], [Version], [IsAutoBackUp], [AutoBackuppath], [BackupDays], [LastBackUpDate], [MinDiffBetweenTwoPunch], [IsAutoShift], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [C8], [C9], [C10], [C11], [C12], [C13], [C14], [C15], [MemoLateEarlySubject], [MemoMissedPunchSubject], [MemoSignature], [MemoAbsentText], [MemoLateEarlyText], [MemoMissedPunchText], [MemoAbsentSubject], [EmployeePhotoPath], [VisitorPhotoPath], [VisitorFingerPrintPath], [VehiclePhotoPath], [IsAutoClearLogs], [MemoHalfDayForLateEarlySubject], [MemoHalfDayForLateEarlyText]) VALUES (1, -1, 0, N'00:00', N'00:00', -1, N'1', N'1', 240, N'nX/XbEFma5sBI5Dz3p9UnfEkxTbXgUeejf+71fKZOLu3i/1+xDjvjtnFF6I4Hdujn5EnI/ciauvvmHTBJ730V0EfGM7e0CW6nYNRecYPQ2RWeriUAkgx1pCoVSLX1O9x9mBkttLHQ5ZLlITFx7W+n8G3OtkS8Ows67TPVQsuSTmk2W0Vg02OVA==', 120, N'eTimeTrackLite 6.5', 0, N'', 1, N'2010-04-27', 5, 0, N'enterprise Software Solutions Lab(eSSL)', N'Bangalore', N' ', N' ', N'http://www.esslindia.com', NULL, NULL, N'', N'', N'', NULL, NULL, NULL, NULL, NULL, N'LATE-COMING/EARLY-GOING NOTICE/MEMO.', N'MISSED OUT PUNCH NOTICE/MEMO.', N'Administrator', N'It has been observed from the Attendance Record that you were Absent from the duty unauthorisedly i.e. without permission on below said attendance date. Please give an explanation to the Authorised person immediately.', N'It has been observed from the Attendance Record that you were  Coming Late or Going Early from the duty unauthorisedly i.e. without permission on below said attendance date. Please give an explanation to the Authorised person immediately.', N'It  has been observed from the Attendance Record that you are not punching properly which is resulting into Missed Out Punch records in our attendance reports. Kindly explain the reason and co-operate with us to know exact out punch.', N'ABSENTEEISM NOTICE/MEMO.', N'', N'', N'', N'', 0, N'HALF DAY FOR LATE-COMING/EARLY-GOING NOTICE/MEMO.', N'It has been observed from the Attendance Record that you were late coming/early going unauthorisedly i.e. without permission on below said attendance date. Hence, we have marked you as Half day.')
SET IDENTITY_INSERT [dbo].[MasterSettings] OFF
/****** Object:  Table [dbo].[MailDetails]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[MailDetails](
	[MaildetailsId] [int] IDENTITY(1,1) NOT NULL,
	[email] [nvarchar](255) NULL,
	[SMTPHost] [nvarchar](255) NULL,
	[Port] [nvarchar](255) NULL,
	[EnableSSL] [int] NULL,
	[SMTPUserName] [nvarchar](255) NULL,
	[SMTPPassword] [nvarchar](255) NULL
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[MailDetails] ON
INSERT [dbo].[MailDetails] ([MaildetailsId], [email], [SMTPHost], [Port], [EnableSSL], [SMTPUserName], [SMTPPassword]) VALUES (1, N'a@a.com', N'SMTPHost', N'0', 0, N'SMTPUserName', N'NgTub+nvAmI=')
SET IDENTITY_INSERT [dbo].[MailDetails] OFF
/****** Object:  Table [dbo].[LogRecordFormat]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[LogRecordFormat](
	[LogFormatId] [int] IDENTITY(1,1) NOT NULL,
	[Status] [nvarchar](255) NULL,
	[FileName] [nvarchar](255) NULL,
	[FileFormat] [nvarchar](255) NULL,
	[Separator] [nvarchar](255) NULL,
	[DataField1] [nvarchar](255) NULL,
	[DataField2] [nvarchar](255) NULL,
	[DataField3] [nvarchar](255) NULL,
	[DataField4] [nvarchar](255) NULL,
	[DataField5] [nvarchar](255) NULL,
	[DataField6] [nvarchar](255) NULL,
	[DataField7] [nvarchar](255) NULL,
	[Format1] [nvarchar](255) NULL,
	[Format2] [nvarchar](255) NULL,
	[Format3] [nvarchar](255) NULL,
	[Format4] [nvarchar](255) NULL,
	[Format5] [nvarchar](255) NULL,
	[Format6] [nvarchar](255) NULL,
	[Format7] [nvarchar](255) NULL,
	[Lbl1] [nvarchar](255) NULL,
	[Lbl2] [nvarchar](255) NULL,
	[InDir] [nvarchar](255) NULL,
	[OutDir] [nvarchar](255) NULL,
	[BreakIn] [nvarchar](255) NULL,
	[BreakOut] [nvarchar](255) NULL,
	[SqlStatus] [nvarchar](255) NULL,
	[MSAccessStatus] [nvarchar](255) NULL,
	[OracleStatus] [nvarchar](255) NULL,
	[DataField8] [nvarchar](255) NULL,
	[Format8] [nvarchar](255) NULL,
	[PrefixFileName] [nvarchar](255) NULL,
	[DataField9] [nvarchar](255) NULL,
	[Format9] [nvarchar](255) NULL,
 CONSTRAINT [LOGFORMAT_PK] PRIMARY KEY CLUSTERED 
(
	[LogFormatId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[LogRecordFormat] ON
INSERT [dbo].[LogRecordFormat] ([LogFormatId], [Status], [FileName], [FileFormat], [Separator], [DataField1], [DataField2], [DataField3], [DataField4], [DataField5], [DataField6], [DataField7], [Format1], [Format2], [Format3], [Format4], [Format5], [Format6], [Format7], [Lbl1], [Lbl2], [InDir], [OutDir], [BreakIn], [BreakOut], [SqlStatus], [MSAccessStatus], [OracleStatus], [DataField8], [Format8], [PrefixFileName], [DataField9], [Format9]) VALUES (1, N'True', N'dd-MM-yyyy', N'dat', N'Tab', N'Employee code', N'Punch DateTime', N'Device Id', N'Direction', N'None', N'None', N'None', N'9', N'dd-MMM-yyyy HH:mm:ss', N'9', N'0', N'', N'', N'', N'lbl_Out_Dir4', N'txt_OutDirSymbol4', N'0', N'1', N'3', N'2', N'False', N'False', N'False', N'', N'', N'', NULL, NULL)
SET IDENTITY_INSERT [dbo].[LogRecordFormat] OFF
/****** Object:  Table [dbo].[LoanRepayments]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[LoanRepayments](
	[LoanRepaymentId] [int] IDENTITY(1,1) NOT NULL,
	[LoanId] [int] NULL,
	[RepaymentMonth] [nvarchar](255) NULL,
	[TotalAmount] [nvarchar](255) NULL,
	[RepaymentYear] [nvarchar](255) NULL,
	[IsAutoDeduct] [int] NULL,
	[Remarks] [nvarchar](4000) NULL,
 CONSTRAINT [LoanRepayments_Pk] PRIMARY KEY CLUSTERED 
(
	[LoanRepaymentId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[LoanDetails]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[LoanDetails](
	[LoanId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeId] [int] NULL,
	[LoanDate] [datetime] NULL,
	[LoanAmount] [nvarchar](255) NULL,
	[LoanType] [nvarchar](255) NULL,
	[InterestRate] [nvarchar](255) NULL,
	[TotalAmount] [nvarchar](255) NULL,
	[Remarks] [nvarchar](4000) NULL,
	[IsSalaryAdvance] [int] NULL,
 CONSTRAINT [LoanDetails_Pk] PRIMARY KEY CLUSTERED 
(
	[LoanId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[LinkageSettings]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[LinkageSettings](
	[LinkageSettingId] [int] IDENTITY(1,1) NOT NULL,
	[LinkageSettingName] [nvarchar](255) NULL,
	[ControllerId] [int] NULL,
	[EventType] [nvarchar](255) NULL,
	[InAddr] [nvarchar](255) NULL,
	[OutType] [nvarchar](255) NULL,
	[OutAddr] [nvarchar](255) NULL,
	[OutTime] [nvarchar](255) NULL,
	[Reserved] [nvarchar](255) NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [LinkageSettings_PK] PRIMARY KEY CLUSTERED 
(
	[LinkageSettingId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[LeaveTypes]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[LeaveTypes](
	[LeaveTypeId] [int] IDENTITY(1,1) NOT NULL,
	[LeaveTypeFName] [nvarchar](50) NOT NULL,
	[LeaveTypeSName] [nvarchar](50) NOT NULL,
	[CarryForwardLimit] [int] NOT NULL,
	[Gender] [nvarchar](255) NOT NULL,
	[YearlyLimit] [nvarchar](50) NOT NULL,
	[ConsiderWeeklyOff] [int] NOT NULL,
	[ConsiderHoliday] [int] NOT NULL,
	[MarkedAs] [nvarchar](255) NULL,
	[Description] [nvarchar](255) NULL,
	[RecordStatus] [int] NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
	[IsAllowNegativeBalance] [int] NULL,
 CONSTRAINT [PK_LeaveTypes] PRIMARY KEY CLUSTERED 
(
	[LeaveTypeId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[LeaveTypes] ON
INSERT [dbo].[LeaveTypes] ([LeaveTypeId], [LeaveTypeFName], [LeaveTypeSName], [CarryForwardLimit], [Gender], [YearlyLimit], [ConsiderWeeklyOff], [ConsiderHoliday], [MarkedAs], [Description], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [IsAllowNegativeBalance]) VALUES (1, N'Casual Leave', N'CL', 5, N'All', N'10', 0, 0, N'Leave', N'', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, -1)
INSERT [dbo].[LeaveTypes] ([LeaveTypeId], [LeaveTypeFName], [LeaveTypeSName], [CarryForwardLimit], [Gender], [YearlyLimit], [ConsiderWeeklyOff], [ConsiderHoliday], [MarkedAs], [Description], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [IsAllowNegativeBalance]) VALUES (2, N'Paid Leave', N'PL', 2, N'All', N'10', 0, 0, N'Leave', N'', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, -1)
INSERT [dbo].[LeaveTypes] ([LeaveTypeId], [LeaveTypeFName], [LeaveTypeSName], [CarryForwardLimit], [Gender], [YearlyLimit], [ConsiderWeeklyOff], [ConsiderHoliday], [MarkedAs], [Description], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [IsAllowNegativeBalance]) VALUES (3, N'SickLeave', N'SL', 0, N'All', N'10', 0, 0, N'Leave', N'a', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, -1)
SET IDENTITY_INSERT [dbo].[LeaveTypes] OFF
/****** Object:  Table [dbo].[LeaveEntries]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[LeaveEntries](
	[LeaveEntryId] [int] IDENTITY(1,1) NOT NULL,
	[LeaveTypeId] [int] NOT NULL,
	[LeaveStatus] [nvarchar](255) NULL,
	[EmployeeId] [int] NOT NULL,
	[FromDate] [datetime] NOT NULL,
	[ToDate] [datetime] NOT NULL,
	[IsApproved] [int] NOT NULL,
	[ApprovedBy] [nvarchar](255) NULL,
	[Remarks] [nvarchar](4000) NULL,
	[LastModifiedBy] [nvarchar](50) NULL,
 CONSTRAINT [PK_LeaveEntries] PRIMARY KEY CLUSTERED 
(
	[LeaveEntryId] ASC,
	[EmployeeId] ASC,
	[FromDate] ASC,
	[ToDate] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Holidays]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Holidays](
	[HolidayId] [int] IDENTITY(1,1) NOT NULL,
	[HolidayName] [nvarchar](50) NOT NULL,
	[CompanyId] [int] NOT NULL,
	[HolidayDate] [datetime] NOT NULL,
	[Description] [nvarchar](255) NULL,
	[HolidayGroups] [nvarchar](255) NULL,
 CONSTRAINT [PK_Holidays] PRIMARY KEY CLUSTERED 
(
	[HolidayId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[FirstCards]    Script Date: 03/11/2013 21:36:31 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[FirstCards](
	[FirstCardId] [int] IDENTITY(1,1) NOT NULL,
	[FirstCardName] [nvarchar](255) NULL,
	[TimeZoneId] [int] NULL,
	[DoorId] [int] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [FirstCards_PK] PRIMARY KEY CLUSTERED 
(
	[FirstCardId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[FirstCardMembers]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[FirstCardMembers](
	[FirstCardMemberId] [int] IDENTITY(1,1) NOT NULL,
	[FirstCardId] [int] NULL,
	[EmployeeId] [int] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [FirstCardMembers_PK] PRIMARY KEY CLUSTERED 
(
	[FirstCardMemberId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ExtraHourShiftAction]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ExtraHourShiftAction](
	[ExtraHourShiftActionId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeId] [int] NULL,
	[Action] [nvarchar](255) NULL,
	[ActionDate] [int] NULL,
	[FromEmployeeId] [int] NULL,
 CONSTRAINT [PK_ExtraHourShiftAction] PRIMARY KEY CLUSTERED 
(
	[ExtraHourShiftActionId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ExtraHourshift]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ExtraHourshift](
	[ExtraHourshiftId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeId] [int] NOT NULL,
	[MultiShiftdate] [datetime] NOT NULL,
	[OnBehalfEmployeeId] [int] NOT NULL,
	[IsCompensated] [int] NOT NULL,
	[CompensatedDate] [datetime] NULL,
	[Remarks] [nvarchar](4000) NULL,
 CONSTRAINT [PK_ExtraHourshift] PRIMARY KEY CLUSTERED 
(
	[ExtraHourshiftId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[EmpShiftFromRosters]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[EmpShiftFromRosters](
	[EmpShiftFromRosterId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeId] [int] NULL,
	[ShiftId] [int] NULL,
	[ShiftDate] [datetime] NULL,
	[ShiftRosterId] [int] NULL,
 CONSTRAINT [EmpShiftFromRosters_PK] PRIMARY KEY CLUSTERED 
(
	[EmpShiftFromRosterId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[EmployeeShift]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[EmployeeShift](
	[EmployeeShiftId] [int] IDENTITY(1,1) NOT NULL,
	[ShiftId] [int] NOT NULL,
	[EmployeeId] [int] NOT NULL,
	[Fromdate] [datetime] NOT NULL,
	[Todate] [datetime] NOT NULL,
	[ShiftType] [nvarchar](50) NOT NULL,
	[LastModifiedBy] [nvarchar](50) NULL,
 CONSTRAINT [PK_EmployeeShift] PRIMARY KEY CLUSTERED 
(
	[EmployeeShiftId] ASC,
	[ShiftId] ASC,
	[EmployeeId] ASC,
	[Fromdate] ASC,
	[Todate] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[EmployeesGreetings]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[EmployeesGreetings](
	[EmployeesGreetingId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeCodeInDevice] [nvarchar](255) NULL,
	[DeviceGreetingId] [int] NULL,
 CONSTRAINT [EmployeesGreetings_PK] PRIMARY KEY CLUSTERED 
(
	[EmployeesGreetingId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[EmployeesBio]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[EmployeesBio](
	[EmployeeBioId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeId] [int] NOT NULL,
	[BioType] [nvarchar](50) NULL,
	[BioVersion] [nvarchar](50) NULL,
	[BioId] [int] NOT NULL,
	[Bio] [ntext] NULL,
 CONSTRAINT [PK_EmployeesBio] PRIMARY KEY CLUSTERED 
(
	[EmployeeBioId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Employees]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Employees](
	[EmployeeId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeName] [nvarchar](50) NOT NULL,
	[EmployeeCode] [nvarchar](50) NOT NULL,
	[StringCode] [nvarchar](50) NOT NULL,
	[NumericCode] [int] NOT NULL,
	[Gender] [nvarchar](255) NOT NULL,
	[CompanyId] [int] NOT NULL,
	[DepartmentId] [int] NOT NULL,
	[Designation] [nvarchar](255) NULL,
	[CategoryId] [int] NOT NULL,
	[DOJ] [datetime] NULL,
	[DOR] [datetime] NULL,
	[DOC] [datetime] NULL,
	[EmployeeCodeInDevice] [nvarchar](50) NOT NULL,
	[EmployeeRFIDNumber] [nvarchar](255) NULL,
	[EmployementType] [nvarchar](255) NOT NULL,
	[Status] [nvarchar](255) NOT NULL,
	[EmployeeDevicePassword] [nvarchar](50) NULL,
	[EmployeeDeviceGroup] [nvarchar](50) NULL,
	[FatherName] [nvarchar](255) NULL,
	[MotherName] [nvarchar](255) NULL,
	[ResidentialAddress] [nvarchar](255) NULL,
	[PermanentAddress] [nvarchar](255) NULL,
	[ContactNo] [nvarchar](255) NULL,
	[Email] [nvarchar](255) NULL,
	[DOB] [datetime] NULL,
	[PlaceOfBirth] [nvarchar](255) NULL,
	[Nomenee1] [nvarchar](255) NULL,
	[Nomenee2] [nvarchar](255) NULL,
	[Remarks] [ntext] NULL,
	[RecordStatus] [int] NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
	[Location] [nvarchar](255) NULL,
	[BLOODGROUP] [nvarchar](255) NULL,
	[WorkPlace] [nvarchar](255) NULL,
	[ExtensionNo] [nvarchar](255) NULL,
	[LoginName] [nvarchar](255) NULL,
	[LoginPassword] [nvarchar](255) NULL,
	[Grade] [nvarchar](255) NULL,
	[Team] [nvarchar](255) NULL,
	[IsRecieveNotification] [int] NULL,
	[HolidayGroup] [int] NULL,
	[ShiftGroupId] [int] NULL,
	[ShiftRosterId] [int] NULL,
	[LastModifiedBy] [nvarchar](50) NULL,
 CONSTRAINT [PK_Employees] PRIMARY KEY CLUSTERED 
(
	[EmployeeId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[Employees] ON
INSERT [dbo].[Employees] ([EmployeeId], [EmployeeName], [EmployeeCode], [StringCode], [NumericCode], [Gender], [CompanyId], [DepartmentId], [Designation], [CategoryId], [DOJ], [DOR], [DOC], [EmployeeCodeInDevice], [EmployeeRFIDNumber], [EmployementType], [Status], [EmployeeDevicePassword], [EmployeeDeviceGroup], [FatherName], [MotherName], [ResidentialAddress], [PermanentAddress], [ContactNo], [Email], [DOB], [PlaceOfBirth], [Nomenee1], [Nomenee2], [Remarks], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [Location], [BLOODGROUP], [WorkPlace], [ExtensionNo], [LoginName], [LoginPassword], [Grade], [Team], [IsRecieveNotification], [HolidayGroup], [ShiftGroupId], [ShiftRosterId], [LastModifiedBy]) VALUES (2545, N'Test Employee1', N'T1', N'T', 1, N'Male', 1, 1, N'', 1, CAST(0x00009DBF00000000 AS DateTime), CAST(0x0006216700000000 AS DateTime), CAST(0x00009DBF00000000 AS DateTime), N'T1', NULL, N'Permanent', N'Working', N'', N'1', N'', N'', N'', N'', N'', N'', CAST(0x0000000000000000 AS DateTime), N'', N'', N'', N'', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, N'', NULL, NULL, NULL, N'', N'', N'', N'', 0, -1, 0, 0, N'')
SET IDENTITY_INSERT [dbo].[Employees] OFF
/****** Object:  Table [dbo].[EmployeePayDetails]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[EmployeePayDetails](
	[EmployeePayDetailid] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeId] [int] NULL,
	[PaymentType] [nvarchar](255) NULL,
	[PanCardNumber] [nvarchar](255) NULL,
	[Bankname] [nvarchar](255) NULL,
	[Bankaccountnumber] [nvarchar](255) NULL,
	[ISCECode] [nvarchar](255) NULL,
	[PFNumber] [nvarchar](255) NULL,
	[ESICNumber] [nvarchar](255) NULL,
	[PFscheme] [nvarchar](255) NULL,
 CONSTRAINT [EmployeePayDetails_Pk] PRIMARY KEY CLUSTERED 
(
	[EmployeePayDetailid] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[EmployeeLeaves]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[EmployeeLeaves](
	[EmployeeLeavesId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeId] [int] NOT NULL,
	[LeaveTypeId] [int] NOT NULL,
	[LeaveYear] [int] NOT NULL,
	[AllowedLeaves] [float] NOT NULL,
 CONSTRAINT [PK_EmployeeLeaves] PRIMARY KEY CLUSTERED 
(
	[EmployeeLeavesId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[EmployeeDepartments]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[EmployeeDepartments](
	[EmployeeDepartmentId] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeId] [int] NULL,
	[DepartmentId] [int] NULL,
 CONSTRAINT [EmployeeDepartment_PK] PRIMARY KEY CLUSTERED 
(
	[EmployeeDepartmentId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[DevicesStatus]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[DevicesStatus](
	[DeviceStatusId] [int] IDENTITY(1,1) NOT NULL,
	[DeviceId] [int] NULL,
	[DeviceStatus] [nvarchar](255) NULL,
	[LastDeviceStatusOn] [datetime] NULL,
 CONSTRAINT [DevicesStatus_PK] PRIMARY KEY CLUSTERED 
(
	[DeviceStatusId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Devices]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Devices](
	[DeviceId] [int] IDENTITY(1,1) NOT NULL,
	[DeviceFName] [nvarchar](255) NOT NULL,
	[DeviceSName] [nvarchar](255) NOT NULL,
	[DeviceDirection] [nvarchar](255) NULL,
	[SerialNumber] [nvarchar](255) NULL,
	[ConnectionType] [nvarchar](255) NULL,
	[IpAddress] [nvarchar](255) NULL,
	[BaudRate] [nvarchar](255) NULL,
	[CommKey] [nvarchar](255) NOT NULL,
	[ComPort] [nvarchar](255) NULL,
	[LastLogDownloadDate] [datetime] NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
	[TransactionStamp] [nvarchar](50) NULL,
	[LastPing] [datetime] NULL,
	[DeviceType] [nvarchar](255) NULL,
	[OpStamp] [nvarchar](255) NULL,
	[DownLoadType] [int] NULL,
	[Timezone] [nvarchar](50) NULL,
	[DeviceLocation] [nvarchar](50) NULL,
	[TimeOut] [nvarchar](50) NULL,
 CONSTRAINT [PK_Devices] PRIMARY KEY CLUSTERED 
(
	[DeviceId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[Devices] ON
INSERT [dbo].[Devices] ([DeviceId], [DeviceFName], [DeviceSName], [DeviceDirection], [SerialNumber], [ConnectionType], [IpAddress], [BaudRate], [CommKey], [ComPort], [LastLogDownloadDate], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [TransactionStamp], [LastPing], [DeviceType], [OpStamp], [DownLoadType], [Timezone], [DeviceLocation], [TimeOut]) VALUES (1, N'Manual Entry(Attendance)', N'ME(Attendance)', N'inout', N'', N'Tcp/IP', N'', N'', N'0', N'', CAST(0x0000000000000000 AS DateTime), NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, CAST(0x0000000000000000 AS DateTime), N'Attendance', NULL, 1, N'330', N'', N'300')
INSERT [dbo].[Devices] ([DeviceId], [DeviceFName], [DeviceSName], [DeviceDirection], [SerialNumber], [ConnectionType], [IpAddress], [BaudRate], [CommKey], [ComPort], [LastLogDownloadDate], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [TransactionStamp], [LastPing], [DeviceType], [OpStamp], [DownLoadType], [Timezone], [DeviceLocation], [TimeOut]) VALUES (2, N'Manual Entry(Canteen)', N'ME(Canteen)', N'inout', N'', N'Tcp/IP', N'', N'', N'0', N'', CAST(0x0000000000000000 AS DateTime), NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, CAST(0x0000000000000000 AS DateTime), N'Canteen', NULL, 1, N'330', N'', N'300')
INSERT [dbo].[Devices] ([DeviceId], [DeviceFName], [DeviceSName], [DeviceDirection], [SerialNumber], [ConnectionType], [IpAddress], [BaudRate], [CommKey], [ComPort], [LastLogDownloadDate], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [TransactionStamp], [LastPing], [DeviceType], [OpStamp], [DownLoadType], [Timezone], [DeviceLocation], [TimeOut]) VALUES (14, N'Test Device', N'TD', N'altinout', N'1', N'Tcp/IP', N'192.168.1.201', N'', N'0', N'', CAST(0x0000000000000000 AS DateTime), NULL, NULL, NULL, NULL, NULL, NULL, NULL, '0', CAST(0x0000000000000000 AS DateTime), N'Attendance', '0', 1, N'330', N'', N'300')
INSERT [dbo].[Devices] ([DeviceId], [DeviceFName], [DeviceSName], [DeviceDirection], [SerialNumber], [ConnectionType], [IpAddress], [BaudRate], [CommKey], [ComPort], [LastLogDownloadDate], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [TransactionStamp], [LastPing], [DeviceType], [OpStamp], [DownLoadType], [Timezone], [DeviceLocation], [TimeOut]) VALUES (15, N'USB Device', N'USB', N'altinout', N'2', N'USB', N'', N'', N'0', N'Com1', CAST(0x0000000000000000 AS DateTime), NULL, NULL, NULL, NULL, NULL, NULL, NULL, '0', CAST(0x0000000000000000 AS DateTime), N'Attendance', '0', 1, N'330', N'', N'300')
SET IDENTITY_INSERT [dbo].[Devices] OFF
/****** Object:  Table [dbo].[DeviceOperationLogTypes]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[DeviceOperationLogTypes](
	[OperationLogTypeId] [int] IDENTITY(1,1) NOT NULL,
	[OperationLogTypeCode] [int] NULL,
	[OperationLogTypeName] [nvarchar](255) NULL,
 CONSTRAINT [DeviceOperationLogTypes_PK] PRIMARY KEY CLUSTERED 
(
	[OperationLogTypeId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[DeviceOperationLogTypes] ON
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (1, 0, N'Power On')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (2, 1, N'Power Off')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (3, 2, N'The Authentication is Failed')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (4, 3, N'Alarm')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (5, 4, N'Enter into the Main Menu')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (6, 5, N'Change The Setting')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (7, 6, N'Enroll a FingerPrint')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (8, 7, N'Enroll a Password')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (9, 8, N'Enroll a HID Card')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (10, 9, N'Delete a User')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (11, 10, N'Delete a FingerPrint')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (12, 11, N'Delete a Password')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (13, 12, N'Delete a RFID Card')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (14, 13, N'Clear the Data')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (15, 14, N'Create a MF Card')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (16, 15, N'Enroll a MF Card')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (17, 16, N'Register  a MF Card')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (18, 17, N'Delete The Registration of MF Card')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (19, 18, N'Clear the MF Cards Content')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (20, 19, N'Move The Enroll Data into Card')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (21, 20, N'Coyp The Data in The Card to The Machine')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (22, 21, N'Set The Time')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (23, 22, N'Factory Setting')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (24, 23, N'Delete The In And Out Record')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (25, 24, N'Clear The Administrator Privilege')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (26, 25, N'Modify The Setting of Access Control Group')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (27, 26, N'Modify The Setting Of User Access Control')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (28, 27, N'Modify The Time Field Of Access Control')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (29, 28, N'Modify The Setting Of Unclock Combination')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (30, 29, N'Unclock')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (31, 30, N'Enroll a User')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (32, 31, N'Change The Finger Prints Attribute')
INSERT [dbo].[DeviceOperationLogTypes] ([OperationLogTypeId], [OperationLogTypeCode], [OperationLogTypeName]) VALUES (33, 32, N'Duress Alarm')
SET IDENTITY_INSERT [dbo].[DeviceOperationLogTypes] OFF
/****** Object:  Table [dbo].[DeviceOperationLogs]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[DeviceOperationLogs](
	[DeviceOperationLogId] [int] IDENTITY(1,1) NOT NULL,
	[DeviceOperationLogCode] [int] NULL,
	[DeviceOperationLogExecutedOn] [datetime] NULL,
	[SerialNumber] [nvarchar](255) NULL,
 CONSTRAINT [DeviceOperationLogs_PK] PRIMARY KEY CLUSTERED 
(
	[DeviceOperationLogId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[DeviceLogs]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[DeviceLogs](
	[DeviceLogId] [int] IDENTITY(1,1) NOT NULL,
	[DownloadDate] [datetime] NULL,
	[DeviceId] [int] NOT NULL,
	[UserId] [nvarchar](50) NOT NULL,
	[LogDate] [datetime] NOT NULL,
	[Direction] [nvarchar](255) NULL,
	[AttDirection] [nvarchar](255) NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
	[WorkCode] [nvarchar](255) NULL,
 CONSTRAINT [PK_DeviceLogs] PRIMARY KEY CLUSTERED 
(
	[DeviceLogId] ASC,
	[UserId] ASC,
	[LogDate] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[DeviceGreetings]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[DeviceGreetings](
	[DeviceGreetingId] [int] IDENTITY(1,1) NOT NULL,
	[GreetingType] [nvarchar](255) NULL,
	[StartTime] [datetime] NULL,
	[ValidMinutes] [int] NULL,
	[DeviceId] [int] NULL,
	[Content] [nvarchar](255) NULL,
 CONSTRAINT [DeviceGreetings_PK] PRIMARY KEY CLUSTERED 
(
	[DeviceGreetingId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[DeviceErrorMessages]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[DeviceErrorMessages](
	[DeviceErrorMessageId] [int] IDENTITY(1,1) NOT NULL,
	[SerialNumber] [nvarchar](50) NULL,
	[ErrorMessage] [nvarchar](500) NULL,
	[LogStream] [nvarchar](4000) NULL,
	[CreatedDate] [nvarchar](50) NULL,
 CONSTRAINT [DeviceErrorMessages_PK] PRIMARY KEY CLUSTERED 
(
	[DeviceErrorMessageId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[DeviceCommands]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[DeviceCommands](
	[DeviceCommandId] [int] IDENTITY(1,1) NOT NULL,
	[Title] [nvarchar](255) NULL,
	[DeviceCommand] [nvarchar](4000) NULL,
	[SerialNumber] [nvarchar](255) NULL,
	[Status] [nvarchar](255) NULL,
	[Type] [nvarchar](255) NULL,
	[CreationDate] [datetime] NULL,
	[ExecutionDate] [datetime] NULL,
 CONSTRAINT [DeviceCommands_PK] PRIMARY KEY CLUSTERED 
(
	[DeviceCommandId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Departments]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Departments](
	[DepartmentId] [int] IDENTITY(1,1) NOT NULL,
	[DepartmentFName] [nvarchar](50) NOT NULL,
	[DepartmentSName] [nvarchar](50) NOT NULL,
	[Description] [nvarchar](50) NULL,
	[RecordStatus] [int] NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
 CONSTRAINT [PK_Departments] PRIMARY KEY CLUSTERED 
(
	[DepartmentId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[Departments] ON
INSERT [dbo].[Departments] ([DepartmentId], [DepartmentFName], [DepartmentSName], [Description], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7]) VALUES (1, N'Default', N'Default', N'', 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL)
SET IDENTITY_INSERT [dbo].[Departments] OFF
/****** Object:  Table [dbo].[Controllers]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Controllers](
	[ControllerId] [int] IDENTITY(1,1) NOT NULL,
	[ControllerName] [nvarchar](255) NULL,
	[Type] [nvarchar](255) NULL,
	[DoorCount] [nvarchar](255) NULL,
	[BuildingLocationId] [int] NULL,
	[IsTCTIP] [int] NULL,
	[IPAddress] [nvarchar](255) NULL,
	[PortNumber] [nvarchar](255) NULL,
	[BaudRate] [nvarchar](255) NULL,
	[SerialPortNumber] [nvarchar](255) NULL,
	[AntiPassback] [int] NULL,
	[Interlock] [int] NULL,
	[AutoSynchronizeDeviceTime] [int] NULL,
	[SwitchTwoDoorway] [int] NULL,
	[LastLogDownloadDate] [datetime] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [Controllers_PK] PRIMARY KEY CLUSTERED 
(
	[ControllerId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ControllerLogs]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ControllerLogs](
	[ControllerLogId] [int] IDENTITY(1,1) NOT NULL,
	[ControllerId] [int] NULL,
	[DownloadDate] [datetime] NULL,
	[LogDate] [datetime] NULL,
	[VerifyType] [nvarchar](255) NULL,
	[InOutState] [nvarchar](255) NULL,
	[UserId] [nvarchar](255) NULL,
	[EventType] [nvarchar](4000) NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [ControllerLogs_PK] PRIMARY KEY CLUSTERED 
(
	[ControllerLogId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ControllerHolidays]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ControllerHolidays](
	[HolidayId] [int] IDENTITY(1,1) NOT NULL,
	[HolidayName] [nvarchar](255) NULL,
	[HolidayTypeId] [int] NULL,
	[HolidayType] [nvarchar](255) NULL,
	[HolidayDate] [datetime] NULL,
	[IsAnnualCycle] [int] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [ControllerHolidays_PK] PRIMARY KEY CLUSTERED 
(
	[HolidayId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ControllerDoors]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ControllerDoors](
	[ControllerDoorId] [int] IDENTITY(1,1) NOT NULL,
	[ControllerId] [int] NULL,
	[DoorName] [nvarchar](255) NULL,
	[DoorNumber] [int] NULL,
	[ValidTimeZoneId] [int] NULL,
	[NormalOpenTimeZoneId] [int] NULL,
	[LockDriveDuration] [int] NULL,
	[PunchInterval] [int] NULL,
	[SensorType] [nvarchar](255) NULL,
	[DoorStatusDelay] [int] NULL,
	[CloseAndReverseLock] [int] NULL,
	[VerifyMode] [nvarchar](255) NULL,
	[DuressPassword] [int] NULL,
	[EmergencyPassword] [int] NULL,
	[CurrentPanel] [int] NULL,
	[AllPanel] [int] NULL,
	[IsAttendance] [int] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [ControllerDoors_PK] PRIMARY KEY CLUSTERED 
(
	[ControllerDoorId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ControllerCommands]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ControllerCommands](
	[ControllerCommandId] [int] IDENTITY(1,1) NOT NULL,
	[ControllerId] [int] NULL,
	[CommandContent] [nvarchar](4000) NULL,
	[CreatedDate] [datetime] NULL,
	[ExecutionDate] [datetime] NULL,
	[Status] [int] NULL,
 CONSTRAINT [ControllerCommands_PK] PRIMARY KEY CLUSTERED 
(
	[ControllerCommandId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[CompanyDepartmentShifts]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[CompanyDepartmentShifts](
	[CompanyDepartmentShiftId] [int] IDENTITY(1,1) NOT NULL,
	[CompanyId] [int] NOT NULL,
	[DepartmentId] [int] NOT NULL,
	[FromDate] [datetime] NOT NULL,
	[ToDate] [datetime] NOT NULL,
	[ShiftId] [int] NOT NULL,
	[ShiftType] [nvarchar](50) NOT NULL,
	[LastModifiedDate] [datetime] NOT NULL,
 CONSTRAINT [PK_CompanyDepartmentShifts] PRIMARY KEY CLUSTERED 
(
	[CompanyDepartmentShiftId] ASC,
	[CompanyId] ASC,
	[DepartmentId] ASC,
	[FromDate] ASC,
	[ToDate] ASC,
	[ShiftId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Companies]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Companies](
	[CompanyId] [int] IDENTITY(1,1) NOT NULL,
	[CompanyFName] [nvarchar](50) NOT NULL,
	[CompanySName] [nvarchar](50) NOT NULL,
	[CompanyAddress] [nvarchar](255) NULL,
	[CompanyIsVisible] [int] NOT NULL,
	[CompanyeMail] [nvarchar](255) NULL,
	[CompanyWebsite] [nvarchar](255) NULL,
	[RecordStatus] [int] NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
 CONSTRAINT [PK_Companies] PRIMARY KEY CLUSTERED 
(
	[CompanyId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[Companies] ON
INSERT [dbo].[Companies] ([CompanyId], [CompanyFName], [CompanySName], [CompanyAddress], [CompanyIsVisible], [CompanyeMail], [CompanyWebsite], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7]) VALUES (1, N'Default', N'Default', N'', -1, NULL, NULL, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL)
SET IDENTITY_INSERT [dbo].[Companies] OFF
/****** Object:  Table [dbo].[Categories]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Categories](
	[CategoryId] [int] IDENTITY(1,1) NOT NULL,
	[CategoryFName] [nvarchar](50) NOT NULL,
	[CategorySName] [nvarchar](50) NOT NULL,
	[OTFormula] [nvarchar](50) NOT NULL,
	[MinOT] [nvarchar](50) NULL,
	[ConsiderFirstLastPunch] [int] NOT NULL,
	[GraceTime] [nvarchar](50) NULL,
	[ConsiderEarlyPunch] [int] NOT NULL,
	[ConsiderLatePunch] [int] NOT NULL,
	[SundayWeeklyOff] [int] NOT NULL,
	[SaturdayWeeklyOff] [int] NOT NULL,
	[WeeklyOff1] [nvarchar](50) NULL,
	[WeeklyOff2] [nvarchar](50) NULL,
	[WhichSaturday] [nvarchar](50) NULL,
	[CalculateHalfDay] [int] NOT NULL,
	[HalfDayMins] [nvarchar](50) NULL,
	[CalculateAbsentDay] [int] NOT NULL,
	[AbsentDayMins] [nvarchar](50) NULL,
	[TransferHPintoCompOff] [int] NOT NULL,
	[TransferWOPintoCompOff] [int] NOT NULL,
	[DeductBreakHours] [int] NOT NULL,
	[ForMissedPunch] [int] NOT NULL,
	[RecordStatus] [int] NOT NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
	[MarkWOandHAsAbsent] [int] NULL,
	[MarkAsAbsentForLate] [int] NULL,
	[ContiousLateDay] [int] NULL,
	[AbsentDayType] [nvarchar](255) NULL,
	[MarkWOandHAsPreDayAbsent] [int] NULL,
	[EarlyGoingGraceTime] [nvarchar](255) NULL,
	[MaxOT] [nvarchar](255) NULL,
	[PCalculateHalfDay] [int] NULL,
	[PHalfDayMins] [nvarchar](255) NULL,
	[PCalculateAbsentDay] [int] NULL,
	[PAbsentDayMins] [nvarchar](255) NULL,
	[MarkWOandHAsBothDayAbsent] [int] NULL,
	[MarkHalfDayForLate] [int] NULL,
	[MarkHalfdayForEarlyGoing] [int] NULL,
	[HalfDayLateByMins] [nvarchar](255) NULL,
	[HalfDayEarlyGoingMins] [nvarchar](255) NULL,
 CONSTRAINT [PK_Categories] PRIMARY KEY CLUSTERED 
(
	[CategoryId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[Categories] ON
INSERT [dbo].[Categories] ([CategoryId], [CategoryFName], [CategorySName], [OTFormula], [MinOT], [ConsiderFirstLastPunch], [GraceTime], [ConsiderEarlyPunch], [ConsiderLatePunch], [SundayWeeklyOff], [SaturdayWeeklyOff], [WeeklyOff1], [WeeklyOff2], [WhichSaturday], [CalculateHalfDay], [HalfDayMins], [CalculateAbsentDay], [AbsentDayMins], [TransferHPintoCompOff], [TransferWOPintoCompOff], [DeductBreakHours], [ForMissedPunch], [RecordStatus], [C1], [C2], [C3], [C4], [C5], [C6], [C7], [MarkWOandHAsAbsent], [MarkAsAbsentForLate], [ContiousLateDay], [AbsentDayType], [MarkWOandHAsPreDayAbsent], [EarlyGoingGraceTime], [MaxOT], [PCalculateHalfDay], [PHalfDayMins], [PCalculateAbsentDay], [PAbsentDayMins], [MarkWOandHAsBothDayAbsent], [MarkHalfDayForLate], [MarkHalfdayForEarlyGoing], [HalfDayLateByMins], [HalfDayEarlyGoingMins]) VALUES (1, N'Default', N'Default', N'Out Punch - Shift End Time', N'30', 0, N'15', -1, -1, -1, -1, N'0', N'6', N'1,2,3,4,5,', -1, N'240', -1, N'120', -1, -1, 0, 0, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, -1, 0, 0, N'', 0, N'15', N'0', 0, N'0', 0, N'0', -1, 0, 0, N'0', N'0')
SET IDENTITY_INSERT [dbo].[Categories] OFF
/****** Object:  Table [dbo].[CanteenTimings]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[CanteenTimings](
	[CanteenTimingId] [int] IDENTITY(1,1) NOT NULL,
	[CanteenTimingName] [nvarchar](255) NULL,
	[CanteenTimingCode] [nvarchar](255) NULL,
	[ItemsAllowed] [nvarchar](2000) NULL,
	[BeginTime] [nvarchar](255) NULL,
	[EndTime] [nvarchar](255) NULL,
	[DefaultItem] [nvarchar](255) NULL,
 CONSTRAINT [CANTEENTIMING_PK] PRIMARY KEY CLUSTERED 
(
	[CanteenTimingId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[CanteenTimings] ON
INSERT [dbo].[CanteenTimings] ([CanteenTimingId], [CanteenTimingName], [CanteenTimingCode], [ItemsAllowed], [BeginTime], [EndTime], [DefaultItem]) VALUES (1, N'Breakfast', N'Breakfast', NULL, N'06:30', N'11:29', N'1')
INSERT [dbo].[CanteenTimings] ([CanteenTimingId], [CanteenTimingName], [CanteenTimingCode], [ItemsAllowed], [BeginTime], [EndTime], [DefaultItem]) VALUES (2, N'Lunch', N'Lunch', NULL, N'11:30', N'15:29', N'2')
INSERT [dbo].[CanteenTimings] ([CanteenTimingId], [CanteenTimingName], [CanteenTimingCode], [ItemsAllowed], [BeginTime], [EndTime], [DefaultItem]) VALUES (3, N'Snacks1', N'Snacks1', NULL, N'15:30', N'18:29', N'3')
INSERT [dbo].[CanteenTimings] ([CanteenTimingId], [CanteenTimingName], [CanteenTimingCode], [ItemsAllowed], [BeginTime], [EndTime], [DefaultItem]) VALUES (4, N'Dinner', N'Dinner', NULL, N'18:30', N'22:29', N'4')
INSERT [dbo].[CanteenTimings] ([CanteenTimingId], [CanteenTimingName], [CanteenTimingCode], [ItemsAllowed], [BeginTime], [EndTime], [DefaultItem]) VALUES (5, N'Snacks2', N'Snacks2', NULL, N'22:30', N'06:29', N'1')
SET IDENTITY_INSERT [dbo].[CanteenTimings] OFF
/****** Object:  Table [dbo].[CanteenItems]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[CanteenItems](
	[CanteenItemId] [int] IDENTITY(1,1) NOT NULL,
	[CanteenItemName] [nvarchar](255) NULL,
	[CanteenItemCode] [nvarchar](255) NULL,
	[CanteenItemSName] [nvarchar](255) NULL,
	[EmployeeContribution] [nvarchar](255) NULL,
	[EmployerContribution] [nvarchar](255) NULL,
 CONSTRAINT [CANTEENITEM_PK] PRIMARY KEY CLUSTERED 
(
	[CanteenItemId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[CanteenItems] ON
INSERT [dbo].[CanteenItems] ([CanteenItemId], [CanteenItemName], [CanteenItemCode], [CanteenItemSName], [EmployeeContribution], [EmployerContribution]) VALUES (1, N'Tea/Coffee', N'1', N'T/C', N'0.75', N'2.00')
INSERT [dbo].[CanteenItems] ([CanteenItemId], [CanteenItemName], [CanteenItemCode], [CanteenItemSName], [EmployeeContribution], [EmployerContribution]) VALUES (2, N'Lunch', N'2', N'Lunch', N'4.25', N'5.75')
INSERT [dbo].[CanteenItems] ([CanteenItemId], [CanteenItemName], [CanteenItemCode], [CanteenItemSName], [EmployeeContribution], [EmployerContribution]) VALUES (3, N'Snacks', N'3', N'Snacks', N'2.75', N'5.25')
INSERT [dbo].[CanteenItems] ([CanteenItemId], [CanteenItemName], [CanteenItemCode], [CanteenItemSName], [EmployeeContribution], [EmployerContribution]) VALUES (4, N'Dinner', N'4', N'Dinner', N'5.00', N'6.00')
SET IDENTITY_INSERT [dbo].[CanteenItems] OFF
/****** Object:  Table [dbo].[BuildingLocations]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[BuildingLocations](
	[BuildingLocationId] [int] IDENTITY(1,1) NOT NULL,
	[BuildingLocationName] [nvarchar](255) NULL,
	[Type] [nvarchar](255) NULL,
	[ParentId] [nvarchar](255) NULL,
	[Description] [nvarchar](255) NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [BuildingLocations_PK] PRIMARY KEY CLUSTERED 
(
	[BuildingLocationId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[AttendanceLogs]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[AttendanceLogs](
	[AttendanceLogId] [int] IDENTITY(1,1) NOT NULL,
	[AttendanceDate] [datetime] NOT NULL,
	[EmployeeId] [int] NOT NULL,
	[InTime] [nvarchar](255) NULL,
	[InDeviceId] [nvarchar](255) NULL,
	[OutTime] [nvarchar](255) NULL,
	[OutDeviceId] [nvarchar](255) NULL,
	[Duration] [float] NOT NULL,
	[LateBy] [int] NOT NULL,
	[EarlyBy] [int] NOT NULL,
	[IsOnLeave] [int] NOT NULL,
	[LeaveType] [nvarchar](50) NULL,
	[LeaveDuration] [float] NULL,
	[WeeklyOff] [int] NOT NULL,
	[Holiday] [int] NOT NULL,
	[LeaveRemarks] [nvarchar](4000) NULL,
	[PunchRecords] [ntext] NOT NULL,
	[ShiftId] [int] NOT NULL,
	[Present] [float] NOT NULL,
	[Absent] [float] NOT NULL,
	[Status] [nvarchar](255) NOT NULL,
	[StatusCode] [nvarchar](255) NOT NULL,
	[P1Status] [nvarchar](255) NULL,
	[P2Status] [nvarchar](255) NULL,
	[P3Status] [nvarchar](255) NULL,
	[IsonSpecialOff] [int] NOT NULL,
	[SpecialOffType] [nvarchar](255) NULL,
	[SpecialOffRemark] [nvarchar](4000) NULL,
	[SpecialOffDuration] [int] NULL,
	[OverTime] [int] NOT NULL,
	[OverTimeE] [int] NOT NULL,
	[MissedOutPunch] [int] NOT NULL,
	[Remarks] [nvarchar](4000) NULL,
	[MissedInPunch] [int] NULL,
	[C1] [nvarchar](255) NULL,
	[C2] [nvarchar](255) NULL,
	[C3] [nvarchar](255) NULL,
	[C4] [nvarchar](255) NULL,
	[C5] [nvarchar](255) NULL,
	[C6] [nvarchar](255) NULL,
	[C7] [nvarchar](255) NULL,
	[LeaveTypeId] [int] NULL,
 CONSTRAINT [PK_AttendanceLogs] PRIMARY KEY CLUSTERED 
(
	[AttendanceLogId] ASC,
	[AttendanceDate] ASC,
	[EmployeeId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
/****** Object:  Table [dbo].[AccessGroups]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[AccessGroups](
	[AccessGroupId] [int] IDENTITY(1,1) NOT NULL,
	[AccessGroupName] [nvarchar](255) NULL,
	[TimeZoneId] [int] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [AccessGroups_PK] PRIMARY KEY CLUSTERED 
(
	[AccessGroupId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[AccessGroupMembers]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[AccessGroupMembers](
	[AccessGroupMemberId] [int] IDENTITY(1,1) NOT NULL,
	[AccessGroupId] [int] NULL,
	[EmployeeId] [int] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [AccessGroupMembers_PK] PRIMARY KEY CLUSTERED 
(
	[AccessGroupMemberId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[AccessGroupDoors]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[AccessGroupDoors](
	[AccessGroupDoorId] [int] IDENTITY(1,1) NOT NULL,
	[AccessGroupId] [int] NULL,
	[ControllerId] [int] NULL,
	[DoorId] [int] NULL,
	[RecordStatus] [int] NULL,
 CONSTRAINT [AccessGroupDoors_PK] PRIMARY KEY CLUSTERED 
(
	[AccessGroupDoorId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[AccessCards]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[AccessCards](
	[AccessCardId] [int] IDENTITY(1,1) NOT NULL,
	[AccessCardNumber] [nvarchar](255) NULL,
	[AccessCardName] [nvarchar](255) NULL,
	[Description] [nvarchar](500) NULL,
 CONSTRAINT [AccessCards_PK] PRIMARY KEY CLUSTERED 
(
	[AccessCardId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[AccessCardDevices]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[AccessCardDevices](
	[AccessCardDeviceId] [int] IDENTITY(1,1) NOT NULL,
	[AccessCardId] [int] NULL,
	[DeviceId] [int] NULL,
	[FromDate] [datetime] NULL,
	[Todate] [datetime] NULL,
	[BeginTime] [nvarchar](255) NULL,
	[EndTime] [nvarchar](255) NULL,
	[TimeZoneIndex] [int] NULL,
 CONSTRAINT [AccessCardDevices_PK] PRIMARY KEY CLUSTERED 
(
	[AccessCardDeviceId] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[WorkCodes]    Script Date: 03/11/2013 21:36:32 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[WorkCodes](
	[WorkCode] [nvarchar](50) NOT NULL,
	[WorKCodeName] [nvarchar](255) NULL,
	[Description] [nvarchar](4000) NULL,
PRIMARY KEY CLUSTERED 
(
	[WorkCode] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
INSERT [dbo].[WorkCodes] ([WorkCode], [WorKCodeName], [Description]) VALUES (N'0', N'0', N'')
/****** Object:  View [dbo].[vw_SpecialEntries]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_SpecialEntries]
AS
SELECT     TOP 100 PERCENT dbo.SpecialEntries.FromDate, dbo.SpecialEntries.ToDate, dbo.SpecialEntries.SpecialType, dbo.SpecialEntries.SpecialEntryStatus, 
                      dbo.Employees.EmployeeName, dbo.SpecialEntries.SpecialEntryId, dbo.Employees.Designation, dbo.Categories.CategorySName, 
                      dbo.Companies.CompanySName, dbo.Departments.DepartmentSName, dbo.Employees.Status, dbo.Employees.NumericCode, 
                      dbo.Employees.StringCode, dbo.Employees.EmployeeCode, dbo.Employees.EmployementType, dbo.Companies.CompanyIsVisible, 
                      dbo.SpecialEntries.Duration, dbo.Companies.CompanyId, dbo.Departments.DepartmentId, dbo.Employees.EmployeeId, dbo.SpecialEntries.Remarks, 
                      dbo.SpecialEntries.IsApproved, dbo.SpecialEntries.BeginTime, dbo.SpecialEntries.EndTime
FROM         dbo.SpecialEntries INNER JOIN
                      dbo.Employees ON dbo.SpecialEntries.EmployeeId = dbo.Employees.EmployeeId INNER JOIN
                      dbo.Categories ON dbo.Employees.CategoryId = dbo.Categories.CategoryId INNER JOIN
                      dbo.Companies ON dbo.Employees.CompanyId = dbo.Companies.CompanyId INNER JOIN
                      dbo.Departments ON dbo.Employees.DepartmentId = dbo.Departments.DepartmentId
WHERE     (dbo.Employees.RecordStatus = 1)
ORDER BY dbo.SpecialEntries.FromDate DESC, dbo.SpecialEntries.ToDate DESC
GO
/****** Object:  View [dbo].[vw_ShiftCalendarShifts]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_ShiftCalendarShifts]
AS
SELECT     TOP 100 PERCENT dbo.Shifts.ShiftSName, dbo.ShiftCalendarShifts.ShiftCalendarShiftId, dbo.ShiftCalendarShifts.ShiftCalendarId, 
                      dbo.ShiftCalendarShifts.ShiftId, dbo.ShiftCalendarShifts.ShiftDate
FROM         dbo.Shifts INNER JOIN
                      dbo.ShiftCalendarShifts ON dbo.Shifts.ShiftId = dbo.ShiftCalendarShifts.ShiftId
ORDER BY dbo.ShiftCalendarShifts.ShiftDate
GO
/****** Object:  View [dbo].[vw_MultiShiftDetails]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_MultiShiftDetails]
AS
SELECT     dbo.ExtraHourshift.*, dbo.Employees.EmployeeName AS EmployeeName, dbo.Employees.EmployeeCode AS EmployeeCode, 
                      Employees_1.EmployeeName AS OnBehalfEmployeeName, dbo.Employees.NumericCode, dbo.Employees.StringCode, 
                      Employees_1.EmployeeCode AS OnBehalfEmployeeCode, dbo.Companies.CompanyId, dbo.Companies.CompanyIsVisible
FROM         dbo.Employees INNER JOIN
                      dbo.ExtraHourshift ON dbo.Employees.EmployeeId = dbo.ExtraHourshift.EmployeeId INNER JOIN
                      dbo.Employees Employees_1 ON dbo.ExtraHourshift.OnBehalfEmployeeId = Employees_1.EmployeeId INNER JOIN
                      dbo.Companies ON dbo.Employees.CompanyId = dbo.Companies.CompanyId INNER JOIN
                      dbo.Companies Companies_1 ON Employees_1.CompanyId = Companies_1.CompanyId
WHERE     (dbo.Employees.RecordStatus = 1) AND (Employees_1.RecordStatus = 1)
GO
/****** Object:  View [dbo].[vw_LeaveEntries]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_LeaveEntries]
AS
SELECT     TOP 100 PERCENT dbo.LeaveEntries.LeaveEntryId, dbo.LeaveTypes.LeaveTypeSName, dbo.LeaveEntries.LeaveStatus, dbo.LeaveEntries.FromDate, 
                      dbo.LeaveEntries.ToDate, dbo.Employees.EmployeeName, dbo.Companies.CompanySName, dbo.Categories.CategorySName, 
                      dbo.Departments.DepartmentSName, dbo.Employees.Status, dbo.Employees.EmployeeCode, dbo.Employees.Designation, 
                      dbo.Employees.EmployementType, dbo.Companies.CompanyIsVisible, dbo.Companies.CompanyId, dbo.Employees.EmployeeId, 
                      dbo.Employees.RecordStatus, dbo.LeaveEntries.LeaveTypeId, dbo.Departments.DepartmentId, dbo.LeaveEntries.Remarks, 
                      dbo.LeaveEntries.IsApproved, dbo.Employees.StringCode, dbo.Employees.NumericCode
FROM         dbo.Employees INNER JOIN
                      dbo.LeaveEntries ON dbo.Employees.EmployeeId = dbo.LeaveEntries.EmployeeId INNER JOIN
                      dbo.LeaveTypes ON dbo.LeaveEntries.LeaveTypeId = dbo.LeaveTypes.LeaveTypeId INNER JOIN
                      dbo.Categories ON dbo.Employees.CategoryId = dbo.Categories.CategoryId INNER JOIN
                      dbo.Companies ON dbo.Employees.CompanyId = dbo.Companies.CompanyId INNER JOIN
                      dbo.Departments ON dbo.Employees.DepartmentId = dbo.Departments.DepartmentId
ORDER BY dbo.LeaveEntries.FromDate DESC, dbo.LeaveEntries.ToDate DESC
GO
/****** Object:  View [dbo].[vw_HoidayDetails]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_HoidayDetails]
AS
SELECT     TOP 100 PERCENT dbo.Holidays.HolidayId, dbo.Holidays.HolidayName, dbo.Holidays.HolidayDate, dbo.Holidays.Description, 
                      dbo.Holidays.CompanyId, dbo.Companies.CompanySName, dbo.Companies.CompanyIsVisible
FROM         dbo.Companies INNER JOIN
                      dbo.Holidays ON dbo.Companies.CompanyId = dbo.Holidays.CompanyId
ORDER BY dbo.Holidays.HolidayDate DESC
GO
/****** Object:  View [dbo].[vw_EmployeeShiftDetails]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_EmployeeShiftDetails]
AS
SELECT     TOP 100 PERCENT dbo.EmployeeShift.EmployeeShiftId, dbo.EmployeeShift.Fromdate, dbo.EmployeeShift.Todate, dbo.Employees.EmployeeName, 
                      dbo.Shifts.ShiftSName, dbo.Departments.DepartmentSName, dbo.Companies.CompanySName, dbo.Categories.CategorySName, 
                      dbo.Employees.Designation, dbo.Employees.Status, dbo.Employees.EmployeeCode, dbo.Employees.NumericCode, dbo.Employees.StringCode, 
                      dbo.Employees.EmployementType, dbo.Companies.CompanyIsVisible, dbo.Shifts.ShiftType, dbo.Companies.CompanyId, dbo.Shifts.ShiftId, 
                      dbo.EmployeeShift.EmployeeId, dbo.Departments.DepartmentId
FROM         dbo.Employees INNER JOIN
                      dbo.EmployeeShift ON dbo.Employees.EmployeeId = dbo.EmployeeShift.EmployeeId INNER JOIN
                      dbo.Shifts ON dbo.EmployeeShift.ShiftId = dbo.Shifts.ShiftId INNER JOIN
                      dbo.Categories ON dbo.Employees.CategoryId = dbo.Categories.CategoryId INNER JOIN
                      dbo.Companies ON dbo.Employees.CompanyId = dbo.Companies.CompanyId INNER JOIN
                      dbo.Departments ON dbo.Employees.DepartmentId = dbo.Departments.DepartmentId
WHERE     (dbo.Employees.RecordStatus = 1)
ORDER BY dbo.EmployeeShift.Fromdate DESC, dbo.EmployeeShift.Todate DESC
GO
/****** Object:  View [dbo].[vw_EmployeeDetails]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_EmployeeDetails]
AS
SELECT     TOP 100 PERCENT dbo.Employees.EmployeeCode, dbo.Employees.EmployeeName, dbo.Employees.EmployeeCodeInDevice, 
                      dbo.Companies.CompanySName, dbo.Departments.DepartmentSName, dbo.Employees.Designation, dbo.Categories.CategorySName, 
                      dbo.Employees.Status, dbo.Employees.EmployementType, dbo.Employees.Gender, dbo.Employees.DOJ, dbo.Employees.DOC, dbo.Employees.DOR, 
                      dbo.Employees.EmployeeId, dbo.Companies.CompanyIsVisible, dbo.Employees.RecordStatus, dbo.Companies.CompanyId, 
                      dbo.Departments.DepartmentId, dbo.Categories.CategoryId, dbo.Employees.EmployeeRFIDNumber, dbo.Employees.StringCode, 
                      dbo.Employees.NumericCode, dbo.Employees.StringCode AS Expr1, dbo.Employees.NumericCode AS Expr2, dbo.Employees.DOB, 
                      dbo.Employees.FatherName, dbo.Employees.MotherName, dbo.Employees.ResidentialAddress, dbo.Employees.ContactNo, dbo.Employees.Email, 
                      dbo.Employees.DOB AS Expr3, dbo.Employees.PlaceOfBirth, dbo.Employees.Nomenee1, dbo.Employees.Nomenee2, 
                      dbo.Employees.PermanentAddress, dbo.Employees.Remarks
FROM         dbo.Categories INNER JOIN
                      dbo.Departments INNER JOIN
                      dbo.Companies INNER JOIN
                      dbo.Employees ON dbo.Companies.CompanyId = dbo.Employees.CompanyId ON dbo.Departments.DepartmentId = dbo.Employees.DepartmentId ON 
                      dbo.Categories.CategoryId = dbo.Employees.CategoryId
ORDER BY dbo.Employees.EmployeeId
GO
/****** Object:  View [dbo].[vw_EmployeeAndCategoryDetails]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_EmployeeAndCategoryDetails]
AS
SELECT     dbo.Employees.EmployeeId, dbo.Employees.EmployeeCode, dbo.Employees.CategoryId, dbo.Categories.CategoryFName, 
                      dbo.Categories.CategorySName, dbo.Categories.OTFormula, dbo.Categories.MinOT, dbo.Categories.ConsiderFirstLastPunch, 
                      dbo.Categories.GraceTime, dbo.Categories.ConsiderEarlyPunch, dbo.Categories.ConsiderLatePunch, dbo.Categories.SundayWeeklyOff, 
                      dbo.Categories.SaturdayWeeklyOff, dbo.Categories.WhichSaturday, dbo.Categories.CalculateHalfDay, dbo.Categories.HalfDayMins, 
                      dbo.Categories.CalculateAbsentDay, dbo.Categories.AbsentDayMins, dbo.Categories.DeductBreakHours, dbo.Categories.RecordStatus, 
                      dbo.Categories.C1, dbo.Categories.C2, dbo.Categories.C3, dbo.Categories.C4, dbo.Categories.C5, dbo.Categories.C6, dbo.Categories.C7, 
                      dbo.Employees.DepartmentId, dbo.Categories.TransferHPintoCompOff, dbo.Categories.TransferWOPintoCompOff, dbo.Categories.ForMissedPunch, 
                      dbo.Employees.StringCode, dbo.Employees.NumericCode, dbo.Employees.DOJ, dbo.Employees.DOC, dbo.Employees.DOR, 
                      dbo.Companies.CompanyId, dbo.Employees.Status, dbo.Employees.EmployeeName
FROM         dbo.Employees INNER JOIN
                      dbo.Categories ON dbo.Employees.CategoryId = dbo.Categories.CategoryId INNER JOIN
                      dbo.Companies ON dbo.Employees.CompanyId = dbo.Companies.CompanyId
GO
/****** Object:  View [dbo].[vw_DeviceLogList]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_DeviceLogList]
AS
SELECT     TOP 100 PERCENT dbo.DeviceLogs.LogDate, dbo.DeviceLogs.DeviceLogId, dbo.Employees.EmployeeId, dbo.DeviceLogs.Direction, 
                      dbo.Devices.DeviceSName, dbo.Employees.EmployeeCode, dbo.Employees.EmployeeCodeInDevice, dbo.Employees.EmployeeName, 
                      dbo.Companies.CompanySName, dbo.Departments.DepartmentSName, dbo.Categories.CategorySName, dbo.Devices.DeviceId, 
                      dbo.Employees.StringCode, dbo.Employees.NumericCode, dbo.Companies.CompanyIsVisible, dbo.Employees.Status, dbo.Employees.Designation, 
                      dbo.Employees.EmployementType, dbo.Departments.DepartmentId, dbo.Companies.CompanyId, dbo.Categories.CategoryId, dbo.DeviceLogs.UserId, 
                      dbo.Employees.RecordStatus, dbo.DeviceLogs.AttDirection
FROM         dbo.DeviceLogs INNER JOIN
                      dbo.Devices ON dbo.DeviceLogs.DeviceId = dbo.Devices.DeviceId INNER JOIN
                      dbo.Employees INNER JOIN
                      dbo.Categories ON dbo.Employees.CategoryId = dbo.Categories.CategoryId INNER JOIN
                      dbo.Companies ON dbo.Employees.CompanyId = dbo.Companies.CompanyId INNER JOIN
                      dbo.Departments ON dbo.Employees.DepartmentId = dbo.Departments.DepartmentId ON 
                      dbo.DeviceLogs.UserId = dbo.Employees.EmployeeCodeInDevice
ORDER BY dbo.DeviceLogs.LogDate DESC
GO
/****** Object:  View [dbo].[vw_CompanyDepartmentShifts]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_CompanyDepartmentShifts]
AS
SELECT     dbo.Departments.DepartmentSName, dbo.Shifts.ShiftSName, dbo.Shifts.ShiftType, dbo.Companies.CompanySName, 
                      dbo.CompanyDepartmentShifts.FromDate, dbo.CompanyDepartmentShifts.ToDate, dbo.CompanyDepartmentShifts.CompanyDepartmentShiftId, 
                      dbo.CompanyDepartmentShifts.LastModifiedDate, dbo.Companies.CompanyId, dbo.Departments.DepartmentId, dbo.Shifts.ShiftId
FROM         dbo.Departments INNER JOIN
                      dbo.Shifts INNER JOIN
                      dbo.Companies INNER JOIN
                      dbo.CompanyDepartmentShifts ON dbo.Companies.CompanyId = dbo.CompanyDepartmentShifts.CompanyId ON 
                      dbo.Shifts.ShiftId = dbo.CompanyDepartmentShifts.ShiftId ON dbo.Departments.DepartmentId = dbo.CompanyDepartmentShifts.DepartmentId
WHERE     (dbo.Departments.RecordStatus = 1) AND (dbo.Companies.RecordStatus = 1)
GO
/****** Object:  View [dbo].[vw_AttendanceLogs]    Script Date: 03/11/2013 21:36:33 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE VIEW [dbo].[vw_AttendanceLogs]
AS
SELECT     dbo.Employees.EmployeeName, dbo.Employees.EmployeeCode, dbo.Employees.StringCode, dbo.Employees.NumericCode, dbo.Employees.Gender, 
                      dbo.Employees.Designation, dbo.Employees.DOJ, dbo.Employees.DOR, dbo.Employees.DOC, dbo.Employees.EmployementType, 
                      dbo.Employees.Status AS EmployeesStatus, dbo.Shifts.ShiftFName, dbo.Shifts.ShiftSName, dbo.Shifts.BeginTime, dbo.Shifts.EndTime, 
                      dbo.Shifts.Break1, dbo.Shifts.Break2, dbo.Shifts.Break1BeginTime, dbo.Shifts.Break2BeginTime, dbo.Shifts.Break1EndTime, 
                      dbo.Shifts.Break2EndTime, dbo.Departments.DepartmentId, dbo.Categories.CategoryId, dbo.Companies.CompanyId, dbo.Companies.CompanySName, 
                      dbo.Categories.CategorySName, dbo.Departments.DepartmentSName, dbo.AttendanceLogs.AttendanceLogId, dbo.AttendanceLogs.AttendanceDate, 
                      dbo.AttendanceLogs.EmployeeId, dbo.AttendanceLogs.InTime, dbo.AttendanceLogs.InDeviceId, dbo.AttendanceLogs.OutTime, 
                      dbo.AttendanceLogs.OutDeviceId, dbo.AttendanceLogs.Duration, dbo.AttendanceLogs.LateBy, dbo.AttendanceLogs.EarlyBy, 
                      dbo.AttendanceLogs.IsOnLeave, dbo.AttendanceLogs.LeaveType, dbo.AttendanceLogs.LeaveDuration, dbo.AttendanceLogs.WeeklyOff, 
                      dbo.AttendanceLogs.Holiday, dbo.AttendanceLogs.LeaveRemarks, dbo.AttendanceLogs.PunchRecords, dbo.AttendanceLogs.ShiftId, 
                      dbo.AttendanceLogs.Present, dbo.AttendanceLogs.Absent, dbo.AttendanceLogs.Status, dbo.AttendanceLogs.StatusCode, dbo.AttendanceLogs.P1Status, 
                      dbo.AttendanceLogs.P2Status, dbo.AttendanceLogs.P3Status, dbo.AttendanceLogs.IsonSpecialOff, dbo.AttendanceLogs.SpecialOffType, 
                      dbo.AttendanceLogs.SpecialOffRemark, dbo.AttendanceLogs.SpecialOffDuration, dbo.AttendanceLogs.OverTime, dbo.AttendanceLogs.OverTimeE, 
                      dbo.AttendanceLogs.MissedOutPunch, dbo.AttendanceLogs.MissedInPunch, dbo.AttendanceLogs.C1, dbo.AttendanceLogs.C3, dbo.AttendanceLogs.C2, 
                      dbo.AttendanceLogs.C4, dbo.AttendanceLogs.C5, dbo.AttendanceLogs.C7
FROM         dbo.Categories INNER JOIN
                      dbo.Departments INNER JOIN
                      dbo.Companies INNER JOIN
                      dbo.AttendanceLogs INNER JOIN
                      dbo.Employees ON dbo.AttendanceLogs.EmployeeId = dbo.Employees.EmployeeId ON dbo.Companies.CompanyId = dbo.Employees.CompanyId ON 
                      dbo.Departments.DepartmentId = dbo.Employees.DepartmentId ON dbo.Categories.CategoryId = dbo.Employees.CategoryId INNER JOIN
                      dbo.Shifts ON dbo.AttendanceLogs.ShiftId = dbo.Shifts.ShiftId
GO
/****** Object:  Default [DF__Visitors__Record__76EBA2E9]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Visitors] ADD  DEFAULT (1) FOR [RecordStatus]
GO
/****** Object:  Default [DF__Vehicles__Record__7D98A078]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Vehicles] ADD  DEFAULT (1) FOR [RecordStatus]
GO
/****** Object:  Default [DF_Users_RecordStatus]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Users] ADD  CONSTRAINT [DF_Users_RecordStatus]  DEFAULT (1) FOR [RecordStatus]
GO
/****** Object:  Default [DF_UserPermissions_UserId]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[UserPermissions] ADD  CONSTRAINT [DF_UserPermissions_UserId]  DEFAULT (0) FOR [UserId]
GO
/****** Object:  Default [DF_UserPermissions_PermissionId]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[UserPermissions] ADD  CONSTRAINT [DF_UserPermissions_PermissionId]  DEFAULT (0) FOR [PermissionId]
GO
/****** Object:  Default [DF_UserCompanies_UserId]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[UserCompanies] ADD  CONSTRAINT [DF_UserCompanies_UserId]  DEFAULT (0) FOR [UserId]
GO
/****** Object:  Default [DF_UserCompanies_CompanyId]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[UserCompanies] ADD  CONSTRAINT [DF_UserCompanies_CompanyId]  DEFAULT (0) FOR [CompanyId]
GO
/****** Object:  Default [DF_SpecialEntries_Duration]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[SpecialEntries] ADD  CONSTRAINT [DF_SpecialEntries_Duration]  DEFAULT (0) FOR [Duration]
GO
/****** Object:  Default [DF_Shifts_Break1]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Shifts] ADD  CONSTRAINT [DF_Shifts_Break1]  DEFAULT (0) FOR [Break1]
GO
/****** Object:  Default [DF_Shifts_Break2]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Shifts] ADD  CONSTRAINT [DF_Shifts_Break2]  DEFAULT (0) FOR [Break2]
GO
/****** Object:  Default [DF_Shifts_ShiftDuration]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Shifts] ADD  CONSTRAINT [DF_Shifts_ShiftDuration]  DEFAULT (0) FOR [ShiftDuration]
GO
/****** Object:  Default [DF_Shifts_Break1Duration]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Shifts] ADD  CONSTRAINT [DF_Shifts_Break1Duration]  DEFAULT (0) FOR [Break1Duration]
GO
/****** Object:  Default [DF_Shifts_Break2Duration]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Shifts] ADD  CONSTRAINT [DF_Shifts_Break2Duration]  DEFAULT (0) FOR [Break2Duration]
GO
/****** Object:  Default [DF_Shifts_RecordStatus]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Shifts] ADD  CONSTRAINT [DF_Shifts_RecordStatus]  DEFAULT (1) FOR [RecordStatus]
GO
/****** Object:  Default [DF__Shifts__PunchBeg__7132C993]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Shifts] ADD  DEFAULT (0) FOR [PunchBeginDuration]
GO
/****** Object:  Default [DF__Shifts__PunchEnd__7226EDCC]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[Shifts] ADD  DEFAULT (0) FOR [PunchEndDuration]
GO
/****** Object:  Default [DF_ShiftCalendarShifts_ShiftCalendarId]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[ShiftCalendarShifts] ADD  CONSTRAINT [DF_ShiftCalendarShifts_ShiftCalendarId]  DEFAULT (0) FOR [ShiftCalendarId]
GO
/****** Object:  Default [DF_ShiftCalendarShifts_ShiftId]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[ShiftCalendarShifts] ADD  CONSTRAINT [DF_ShiftCalendarShifts_ShiftId]  DEFAULT (0) FOR [ShiftId]
GO
/****** Object:  Default [DF_ShiftCalendarShifts_ShiftDate]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[ShiftCalendarShifts] ADD  CONSTRAINT [DF_ShiftCalendarShifts_ShiftDate]  DEFAULT (0) FOR [ShiftDate]
GO
/****** Object:  Default [DF_MasterSettings_LastBackUpDate]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[MasterSettings] ADD  CONSTRAINT [DF_MasterSettings_LastBackUpDate]  DEFAULT ('1900-01-01') FOR [LastBackUpDate]
GO
/****** Object:  Default [DF_MasterSettings_IsAutoShift]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[MasterSettings] ADD  CONSTRAINT [DF_MasterSettings_IsAutoShift]  DEFAULT (0) FOR [IsAutoShift]
GO
/****** Object:  Default [DF_LeaveTypes_CarryForwardLimit]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[LeaveTypes] ADD  CONSTRAINT [DF_LeaveTypes_CarryForwardLimit]  DEFAULT (0) FOR [CarryForwardLimit]
GO
/****** Object:  Default [DF_LeaveTypes_YearlyLimit]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[LeaveTypes] ADD  CONSTRAINT [DF_LeaveTypes_YearlyLimit]  DEFAULT (0) FOR [YearlyLimit]
GO
/****** Object:  Default [DF_LeaveTypes_RecordStatus]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[LeaveTypes] ADD  CONSTRAINT [DF_LeaveTypes_RecordStatus]  DEFAULT (1) FOR [RecordStatus]
GO
/****** Object:  Default [DF_LeaveEntries_LeaveTypeId]    Script Date: 03/11/2013 21:36:31 ******/
ALTER TABLE [dbo].[LeaveEntries] ADD  CONSTRAINT [DF_LeaveEntries_LeaveTypeId]  DEFAULT (0) FOR [LeaveTypeId]
GO
/****** Object:  Default [DF_ExtraHourshift_EmployeeId]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[ExtraHourshift] ADD  CONSTRAINT [DF_ExtraHourshift_EmployeeId]  DEFAULT (0) FOR [EmployeeId]
GO
/****** Object:  Default [DF_Employees_DOJ]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_DOJ]  DEFAULT ('1900-01-01') FOR [DOJ]
GO
/****** Object:  Default [DF_Employees_DOR]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_DOR]  DEFAULT ('1900-01-01') FOR [DOR]
GO
/****** Object:  Default [DF_Employees_DOC]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_DOC]  DEFAULT ('1900-01-01') FOR [DOC]
GO
/****** Object:  Default [DF_Employees_EmployeeDevicePassword]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_EmployeeDevicePassword]  DEFAULT ('') FOR [EmployeeDevicePassword]
GO
/****** Object:  Default [DF_Employees_EmployeeDeviceGroup]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_EmployeeDeviceGroup]  DEFAULT (1) FOR [EmployeeDeviceGroup]
GO
/****** Object:  Default [DF_Employees_FatherName]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_FatherName]  DEFAULT ('') FOR [FatherName]
GO
/****** Object:  Default [DF_Employees_MotherName]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_MotherName]  DEFAULT ('') FOR [MotherName]
GO
/****** Object:  Default [DF_Employees_ResidentialAddress]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_ResidentialAddress]  DEFAULT ('') FOR [ResidentialAddress]
GO
/****** Object:  Default [DF_Employees_PermanentAddress]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_PermanentAddress]  DEFAULT ('') FOR [PermanentAddress]
GO
/****** Object:  Default [DF_Employees_ContactNo]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_ContactNo]  DEFAULT ('') FOR [ContactNo]
GO
/****** Object:  Default [DF_Employees_Email]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_Email]  DEFAULT ('') FOR [Email]
GO
/****** Object:  Default [DF_Employees_DOB]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_DOB]  DEFAULT ('1900-01-01') FOR [DOB]
GO
/****** Object:  Default [DF_Employees_PlaceOfBirth]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_PlaceOfBirth]  DEFAULT ('') FOR [PlaceOfBirth]
GO
/****** Object:  Default [DF_Employees_Nomenee1]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_Nomenee1]  DEFAULT ('') FOR [Nomenee1]
GO
/****** Object:  Default [DF_Employees_Nomenee2]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_Nomenee2]  DEFAULT ('') FOR [Nomenee2]
GO
/****** Object:  Default [DF_Employees_Remarks]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_Remarks]  DEFAULT ('') FOR [Remarks]
GO
/****** Object:  Default [DF_Employees_RecordStatus]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Employees] ADD  CONSTRAINT [DF_Employees_RecordStatus]  DEFAULT (1) FOR [RecordStatus]
GO
/****** Object:  Default [DF_Devices_CommKey]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Devices] ADD  CONSTRAINT [DF_Devices_CommKey]  DEFAULT (0) FOR [CommKey]
GO
/****** Object:  Default [DF_Devices_LastLogDownloadDate]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Devices] ADD  CONSTRAINT [DF_Devices_LastLogDownloadDate]  DEFAULT ('1900-01-01 00:00') FOR [LastLogDownloadDate]
GO
/****** Object:  Default [DF__Devices__Transac__703EA55A]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Devices] ADD  DEFAULT ('0') FOR [TransactionStamp]
GO
/****** Object:  Default [DF_Departments_RecordStatus]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Departments] ADD  CONSTRAINT [DF_Departments_RecordStatus]  DEFAULT (1) FOR [RecordStatus]
GO
/****** Object:  Default [DF_CompanyDepartmentShifts_LastModifiedDate]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[CompanyDepartmentShifts] ADD  CONSTRAINT [DF_CompanyDepartmentShifts_LastModifiedDate]  DEFAULT ('1900-01-01') FOR [LastModifiedDate]
GO
/****** Object:  Default [DF_Companies_RecordStatus]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Companies] ADD  CONSTRAINT [DF_Companies_RecordStatus]  DEFAULT (1) FOR [RecordStatus]
GO
/****** Object:  Default [DF_Categories_RecordStatus]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[Categories] ADD  CONSTRAINT [DF_Categories_RecordStatus]  DEFAULT (1) FOR [RecordStatus]
GO
/****** Object:  Default [DF_AttendanceLogs_Duration]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_Duration]  DEFAULT (0) FOR [Duration]
GO
/****** Object:  Default [DF_AttendanceLogs_LateBy]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_LateBy]  DEFAULT (0) FOR [LateBy]
GO
/****** Object:  Default [DF_AttendanceLogs_EarlyBy]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_EarlyBy]  DEFAULT (0) FOR [EarlyBy]
GO
/****** Object:  Default [DF_AttendanceLogs_WeeklyOff]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_WeeklyOff]  DEFAULT (0) FOR [WeeklyOff]
GO
/****** Object:  Default [DF_AttendanceLogs_Holiday]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_Holiday]  DEFAULT (0) FOR [Holiday]
GO
/****** Object:  Default [DF_AttendanceLogs_ShiftId]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_ShiftId]  DEFAULT (0) FOR [ShiftId]
GO
/****** Object:  Default [DF_AttendanceLogs_Present]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_Present]  DEFAULT (0) FOR [Present]
GO
/****** Object:  Default [DF_AttendanceLogs_Absent]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_Absent]  DEFAULT (0) FOR [Absent]
GO
/****** Object:  Default [DF_AttendanceLogs_OverTime]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_OverTime]  DEFAULT (0) FOR [OverTime]
GO
/****** Object:  Default [DF_AttendanceLogs_OverTimeE]    Script Date: 03/11/2013 21:36:32 ******/
ALTER TABLE [dbo].[AttendanceLogs] ADD  CONSTRAINT [DF_AttendanceLogs_OverTimeE]  DEFAULT (0) FOR [OverTimeE]
GO

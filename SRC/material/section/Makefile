include ../../../Makefile.def

OBJS       = SectionForceDeformation.o \
	ElasticSection2d.o ElasticSection3d.o \
	ElasticShearSection2d.o ElasticShearSection3d.o \
	ElasticBDShearSection2d.o \
	ElasticWarpingShearSection2d.o \
	ElasticTubeSection3d.o \
	GenericSection1d.o \
	SectionAggregator.o \
	ParallelSection.o \
	ElasticPlateSection.o \
	ElasticMembranePlateSection.o \
	MembranePlateFiberSection.o \
	TclModelBuilderSectionCommand.o \
	FiberSection2d.o \
	NDFiberSection2d.o \
	NDFiberSection3d.o \
	NDFiberSectionWarping2d.o \
	FiberSection2dThermal.o \
	FiberSection3d.o \
	FiberSectionGJ.o \
	Bidirectional.o \
	Elliptical.o \
	Elliptical2.o \
	TimoshenkoSection3d.o \
	Isolator2spring.o \
	McftSection2dfiber.o \
	LayeredShellFiberSection.o \
	LayeredShellFiberSectionThermal.o \
	FiberSection3dThermal.o \
	MembranePlateFiberSectionThermal.o \
	FiberSectionGJThermal.o

all:         $(OBJS)
	@$(CD) $(FE)/material/section/repres; $(MAKE);
	@$(CD) $(FE)/material/section/fiber; $(MAKE);
	@$(CD) $(FE)/material/section/yieldSurface; $(MAKE);
	@$(CD) $(FE)/material/section/integration; $(MAKE);

test: main.o
	@$(LINKER) $(LINKFLAGS) main.o $(INTERPRETER_LIBS_MPI) \
	$(FE_LIBRARY) $(MACHINE_LINKLIBS) $(PARALLEL_LIB) \
	$(MACHINE_NUMERICAL_LIBS) $(TCL_LIBRARY)  \
	$(MACHINE_SPECIFIC_LIBS) -o section_tst

# Miscellaneous

tidy:   
	@$(RM) $(RMFLAGS) Makefile.bak *~ #*# core

clean: tidy
	@$(RM) $(RMFLAGS) $(OBJS) *.o

spotless: clean

wipe: spotless
	@$(CD) $(FE)/material/section/repres; $(MAKE) wipe;
	@$(CD) $(FE)/material/section/fiber; $(MAKE) wipe;
	@$(CD) $(FE)/material/section/yieldSurface; $(MAKE) wipe;
	@$(CD) $(FE)/material/section/integration; $(MAKE) wipe;

# DO NOT DELETE THIS LINE -- make depends on it.

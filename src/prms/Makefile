# prms library makefile

include ../makelist
PRMSLIB = $(LIBDIR)/libprmsiv.a
MMFLIB	 = $(LIBDIR)/libmmf.a
LIBS	= $(PRMSLIB) $(MMFLIB) $(FLIBS)

####################################################
# Rules for targets
####################################################
all: $(PRMSLIB)

$(TARGET): $(PRMSLIB)
	$(RM) $(TARGET)

$(MMFLIB):
	$(CD) $(MMFDIR);make

#
# Define all object files which make up the library
#
LIBOBJS = \
        basin.o \
        climateflow_gu.o \
        cascade_gu.o \
        soltab.o \
        prms_time_gu.o \
        obs_gu.o \
        climate_hru.o \
        potet_jh.o \
        potet_pt.o \
        potet_hs.o \
        potet_pm.o \
        potet_pm_sta.o \
        potet_pan.o \
        potet_hamon.o \
        ddsolrad.o \
        ccsolrad.o \
        ide_dist.o \
        xyz_dist.o \
        precip_1sta_laps.o \
        precip_dist2.o \
        temp_1sta_laps.o \
        temp_dist2.o \
        transp_frost.o \
        transp_tindex.o \
        frost_date.o \
        intcp_gu.o \
        snowcomp.o \
        srunoff_gu.o \
	srunoff_urban_gu.o \
        soilzone_gu.o \
        gwflow_gu.o \
        water_balance_gu.o \
        routing.o \
        strmflow.o \
        strmflow_in_out.o \
        muskingum.o \
        subbasin.o \
        map_results_gu.o \
        nhru_summary.o \
        write_climate_hru.o \
        nsub_summary.o \
        nsegment_summary.o \
        basin_summary.o \
        basin_sum.o \
        utils_prms.o

install: lib

lib: $(PRMSLIB)

$(PRMSLIB): $(LIBOBJS)
	$(RM) $(PRMSLIB)
	$(AR) $(PRMSLIB) $(LIBOBJS)
	$(RANLIB) $(PRMSLIB)

clean:
	$(RM) $(PRMSLIB)
	$(RM) *.o *.mod *~

basin_sum.o: basin_sum.f90 prms_module.mod prms_flowvars.mod prms_intcp_gu.mod prms_snow.mod prms_srunoff_gu.mod prms_gwflow_gu.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod prms_obs_gu.mod prms_muskingum.mod
	$(FC) -c $(FFLAGS) basin_sum.f90

subbasin.o: subbasin.f90 prms_module.mod prms_basin.mod prms_flowvars.mod prms_set_time.mod prms_intcp_gu.mod prms_srunoff_gu.mod prms_soilzone_gu.mod prms_gwflow_gu.mod prms_snow.mod prms_climatevars.mod 
	$(FC) -c $(FFLAGS) subbasin.f90

ddsolrad.o: ddsolrad.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_soltab.mod prms_set_time.mod prms_obs_gu.mod
	$(FC) -c $(FFLAGS) ddsolrad.f90

ccsolrad.o: ccsolrad.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_soltab.mod prms_set_time.mod prms_obs_gu.mod
	$(FC) -c $(FFLAGS) ccsolrad.f90

snowcomp.o: snowcomp.f90 prms_module.mod prms_basin.mod prms_flowvars.mod prms_climatevars.mod prms_set_time.mod prms_intcp_gu.mod
	$(FC) -c $(FFLAGS) snowcomp.f90

gwflow_gu.o: gwflow_gu.f90 prms_module.mod prms_basin.mod prms_flowvars.mod prms_intcp_gu.mod prms_srunoff_gu.mod prms_soilzone_gu.mod prms_cascade_gu.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) gwflow_gu.f90

utils_prms.o: utils_prms.f90 prms_module.mod prms_basin.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) utils_prms.f90

prms_summary.o: prms_summary.f90 prms_module.mod prms_climatevars.mod prms_flowvars.mod prms_set_time.mod prms_obs_gu.mod prms_intcp_gu.mod prms_snow.mod prms_srunoff_gu.mod prms_soilzone_gu.mod prms_gwflow_gu.mod
	$(FC) -c $(FFLAGS) prms_summary.f90

muskingum.o: muskingum.f90 prms_module.mod prms_basin.mod prms_flowvars.mod prms_set_time.mod prms_obs_gu.mod prms_srunoff_gu.mod prms_gwflow_gu.mod
	$(FC) -c $(FFLAGS) muskingum.f90

intcp_gu.o: intcp_gu.f90 prms_module.mod prms_basin.mod prms_obs_gu.mod prms_climatevars.mod prms_flowvars.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) intcp_gu.f90

map_results_gu.o: map_results_gu.f90 prms_module.mod prms_basin.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) map_results_gu.f90

nhru_summary.o: nhru_summary.f90 prms_module.mod prms_basin.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) nhru_summary.f90

nsub_summary.o: nsub_summary.f90 prms_module.mod prms_basin.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) nsub_summary.f90

nsegment_summary.o: nsegment_summary.f90 prms_module.mod prms_basin.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) nsegment_summary.f90

basin_summary.o: basin_summary.f90 prms_module.mod prms_basin.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) basin_summary.f90

soltab.o: soltab.f90 prms_module.mod prms_basin.mod
	$(FC) -c $(FFLAGS) soltab.f90

frost_date.o: frost_date.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) frost_date.f90

precip_1sta_laps.o: precip_1sta_laps.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod prms_obs_gu.mod
	$(FC) -c $(FFLAGS) precip_1sta_laps.f90

transp_tindex.o: transp_tindex.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) transp_tindex.f90

transp_frost.o: transp_frost.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) transp_frost.f90

temp_1sta_laps.o: temp_1sta_laps.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod prms_obs_gu.mod
	$(FC) -c $(FFLAGS) temp_1sta_laps.f90

temp_dist2.o: temp_dist2.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod prms_obs_gu.mod
	$(FC) -c $(FFLAGS) temp_dist2.f90

precip_dist2.o: precip_dist2.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod prms_obs_gu.mod
	$(FC) -c $(FFLAGS) precip_dist2.f90

strmflow.o: strmflow.f90 prms_module.mod prms_basin.mod prms_obs_gu.mod prms_flowvars.mod prms_gwflow_gu.mod prms_srunoff_gu.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) strmflow.f90

strmflow_in_out.o: strmflow_in_out.f90 prms_module.mod prms_basin.mod prms_obs_gu.mod prms_flowvars.mod prms_gwflow_gu.mod prms_srunoff_gu.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) strmflow_in_out.f90

potet_jh.o: potet_jh.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) potet_jh.f90

potet_pt.o: potet_pt.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_soltab.mod prms_set_time.mod prms_climate_hru.mod
	$(FC) -c $(FFLAGS) potet_pt.f90

potet_hs.o: potet_hs.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) potet_hs.f90

potet_pm.o: potet_pm.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_soltab.mod prms_set_time.mod prms_climate_hru.mod
	$(FC) -c $(FFLAGS) potet_pm.f90

potet_pm_sta.o: potet_pm_sta.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_climate_hru.mod prms_soltab.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) potet_pm_sta.f90

potet_pan.o: potet_pan.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_obs_gu.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) potet_pan.f90

potet_hamon.o: potet_hamon.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_soltab.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) potet_hamon.f90

write_climate_hru.o: write_climate_hru.f90  prms_module.mod prms_set_time.mod prms_climatevars.mod
	$(FC) -c $(FFLAGS) write_climate_hru.f90

climate_hru.o: climate_hru.f90 prms_module.mod prms_basin.mod prms_climatevars.mod prms_soltab.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) climate_hru.f90

cascade_gu.o: cascade_gu.f90 prms_module.mod prms_basin.mod
	$(FC) -c $(FFLAGS) cascade_gu.f90

basin.o: basin.f90 prms_module.mod
	$(FC) -c $(FFLAGS) basin.f90

obs_gu.o: obs_gu.f90 prms_module.mod prms_set_time.mod prms_basin.mod
	$(FC) -c $(FFLAGS) obs_gu.f90

srunoff_gu.o: srunoff_gu.f90 prms_module.mod prms_basin.mod prms_flowvars.mod prms_climatevars.mod prms_cascade_gu.mod prms_intcp_gu.mod prms_snow.mod prms_set_time.mod srunoff_urban_gu.mod
	$(FC) -c $(FFLAGS) srunoff_gu.f90
	
srunoff_urban_gu.o: srunoff_urban_gu.f90 prms_module.mod prms_basin.mod
	$(FC) -c $(FFLAGS) srunoff_urban_gu.f90	

climateflow_gu.o: climateflow_gu.f90 prms_module.mod prms_basin.mod prms_set_time.mod
	$(FC) -c $(FFLAGS) climateflow_gu.f90

soilzone_gu.o: soilzone_gu.f90 prms_module.mod prms_basin.mod prms_flowvars.mod prms_snow.mod prms_climatevars.mod prms_cascade_gu.mod prms_set_time.mod prms_intcp_gu.mod prms_srunoff_gu.mod srunoff_urban_gu.mod
	$(FC) -c $(FFLAGS) soilzone_gu.f90

routing.o: routing.f90 prms_module.mod prms_basin.mod prms_gwflow_gu.mod prms_flowvars.mod prms_set_time.mod prms_srunoff_gu.mod prms_climatevars.mod
	$(FC) -c $(FFLAGS) routing.f90

prms_time_gu.o: prms_time_gu.f90 prms_module.mod prms_basin.mod
	$(FC) -c $(FFLAGS) prms_time_gu.f90

water_balance_gu.o: water_balance_gu.f90 prms_module.mod prms_basin.mod prms_srunoff_gu.mod prms_flowvars.mod prms_gwflow_gu.mod prms_climatevars.mod prms_set_time.mod prms_cascade_gu.mod prms_intcp_gu.mod prms_snow.mod prms_soilzone_gu.mod srunoff_urban_gu.mod
	$(FC) -c $(FFLAGS) water_balance_gu.f90

prms_climatevars.mod: climateflow_gu.o
prms_flowvars.mod: climateflow_gu.o
prms_gwflow_gu.mod: gwflow_gu.o
prms_module.mod:
	$(CD) ../gsflow;make prms_module.mod
	$(CP) ../gsflow/prms_module.mod .
prms_obs_gu.mod: obs_gu.o
prms_basin.mod: basin.o
prms_soltab.mod: soltab.o
prms_muskingum.mod: muskingum.o
prms_intcp_gu.mod: intcp_gu.o
prms_snow.mod: snowcomp.o
prms_cascade_gu.mod: cascade_gu.o
prms_set_time.mod: prms_time_gu.o
prms_soilzone_gu.mod: soilzone_gu.o
prms_srunoff_gu.mod: srunoff_gu.o
srunoff_urban_gu.mod: srunoff_urban_gu.o

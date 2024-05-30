V1PA=V1PA_Historical_Paradigm
V1PB=V1PB_Modern_Paradigm
V1PC=V1PC_Software_Engineering
V2PA=V2PA_Remote_Desktop
V2PB=V2PB_Hardware_Sharing
V2PC=V2PC_Distributed_Framework
V2PD=V2PD_Physical_Layer

all:
	cd $(V1PA) && $(MAKE) thorough
	cd $(V1PB) && $(MAKE) thorough
	cd $(V1PC) && $(MAKE) thorough
	cd $(V2PA) && $(MAKE) thorough
	cd $(V2PB) && $(MAKE) thorough
	cd $(V2PC) && $(MAKE) thorough
	cd $(V2PD) && $(MAKE) thorough

clean:
	cd $(V1PA) && $(MAKE) clean
	cd $(V1PB) && $(MAKE) clean
	cd $(V1PC) && $(MAKE) clean
	cd $(V2PA) && $(MAKE) clean
	cd $(V2PB) && $(MAKE) clean
	cd $(V2PC) && $(MAKE) clean
	cd $(V2PD) && $(MAKE) clean


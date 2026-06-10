#!/bin/bash
RED='\033[1;31m'
GRN='\033[1;32m'
BLU='\033[1;34m'
YEL='\033[1;33m'
PUR='\033[1;35m'
CYAN='\033[1;36m'
NC='\033[0m'

echo -e "${CYAN}*---------------------*----------------------*${NC}"
echo -e "${YEL}*   Check MDM - Skip MDM Auto for MacOS by   *${NC}"
echo -e "${RED}*               SKIPMDM.COM                  *${NC}"
echo -e "${RED}*              Phoenix Team                  *${NC}"
echo -e "${GRN}*          Modified by Dat Pham Tat          *${NC}"
echo -e "${GRN}*  Please use for Device that have data ONLY *${NC}"
echo -e "${CYAN}*---------------------*----------------------*${NC}"
echo ""
PS3='Please enter your choice: '
options=("Autoypass on Recovery" "Reboot")
select opt in "${options[@]}"; do
	case $opt in
	"Autoypass on Recovery")
		echo -e "${GRN}Bypass on Recovery"
		echo "0.0.0.0 deviceenrollment.apple.com" >>/Volumes/Macintosh\ HD/etc/hosts
		echo "0.0.0.0 mdmenrollment.apple.com" >>/Volumes/Macintosh\ HD/etc/hosts
		echo "0.0.0.0 iprofiles.apple.com" >>/Volumes/Macintosh\ HD/etc/hosts
        echo -e "${GREEN}Successfully blocked host / Thành công chặn host${NC}"
		# echo "Remove config profile"
  	touch /Volumes/Data/private/var/db/.AppleSetupDone
        rm -rf /Volumes/Macintosh\ HD/var/db/ConfigurationProfiles/Settings/.cloudConfigHasActivationRecord
	rm -rf /Volumes/Macintosh\ HD/var/db/ConfigurationProfiles/Settings/.cloudConfigRecordFound
	touch /Volumes/Macintosh\ HD/var/db/ConfigurationProfiles/Settings/.cloudConfigProfileInstalled
	touch /Volumes/Macintosh\ HD/var/db/ConfigurationProfiles/Settings/.cloudConfigRecordNotFound
	echo -e "${CYAN}------ Autobypass SUCCESSFULLY / Autobypass HOÀN TẤT ------${NC}"
	echo -e "${CYAN}------ Exit Terminal , Reset Macbook and ENJOY ! ------${NC}"
		break
		;;
    "Disable Notification (SIP)")
    	echo -e "${RED}Please Insert Your Password To Proceed${NC}"
        sudo rm /var/db/ConfigurationProfiles/Settings/.cloudConfigHasActivationRecord
        sudo rm /var/db/ConfigurationProfiles/Settings/.cloudConfigRecordFound
        sudo touch /var/db/ConfigurationProfiles/Settings/.cloudConfigProfileInstalled
        sudo touch /var/db/ConfigurationProfiles/Settings/.cloudConfigRecordNotFound
        break
        ;;
    "Disable Notification (Recovery)")
        rm -rf /Volumes/Macintosh\ HD/var/db/ConfigurationProfiles/Settings/.cloudConfigHasActivationRecord
	rm -rf /Volumes/Macintosh\ HD/var/db/ConfigurationProfiles/Settings/.cloudConfigRecordFound
	touch /Volumes/Macintosh\ HD/var/db/ConfigurationProfiles/Settings/.cloudConfigProfileInstalled
	touch /Volumes/Macintosh\ HD/var/db/ConfigurationProfiles/Settings/.cloudConfigRecordNotFound

        break
        ;;
	"Check MDM Enrollment")
		echo ""
		echo -e "${GRN}Check MDM Enrollment. Error is success${NC}"
		echo ""
		echo -e "${RED}Please Insert Your Password To Proceed${NC}"
		echo ""
		sudo profiles show -type enrollment
		break
		;;
	"Exit")
 		echo "Rebooting..."
		reboot
		break
		;;
	*) echo "Invalid option $REPLY" ;;
	esac
done

################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include uart/subdir.mk
-include timer0_pwm/subdir.mk
-include timer0_ovf/subdir.mk
-include eeprom/i2c/subdir.mk
-include eeprom/subdir.mk
-include dc_motor/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
control_ecu.lss \

SIZEDUMMY += \
sizedummy \


# All Target
all: control_ecu.elf secondary-outputs

# Tool invocations
control_ecu.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,control_ecu.map -mmcu=atmega16 -o "control_ecu.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

control_ecu.lss: control_ecu.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S control_ecu.elf  >"control_ecu.lss"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: control_ecu.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega16 control_ecu.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(ELFS)$(OBJS)$(ASM_DEPS)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) control_ecu.elf
	-@echo ' '

secondary-outputs: $(LSS) $(SIZEDUMMY)

.PHONY: all clean dependents

-include ../makefile.targets

PACKAGE_NAME = @PACKAGE_NAME@

desktopdir = ${HOME}/.cnbitk/$(PACKAGE_NAME)/desktop
desktop_DATA = CNBILoop-AntNeuro-32EEG.desktop \
			   CNBILoop-AntNeuro-64EEG.desktop \
			   CNBIMobileProtocols.desktop \
			   CNBIMobileResting.desktop \
			   CNBIWheelchairJoystick.desktop \
			   CNBIWheelchairNavigationDemo.desktop \
			   eegview-AntNeuro-32EEG.desktop \
			   eegview-AntNeuro-64EEG.desktop \
			   CNBILoop-Close.desktop \
			   CNBIWheelchairVisualization.desktop

install-exec-local:
	cp *.desktop ${HOME}/Desktop/ 

uninstall-local:
	cd ${HOME}/Desktop && \
	rm -f CNBILoop-AntNeuro-32EEG.desktop && \
	rm -f CNBILoop-AntNeuro-64EEG.desktop && \
	rm -f CNBIMobileProtocols.desktop && \
	rm -f CNBIWheelchairJoystick.desktop && \
	rm -f CNBIWheelchairNavigationDemo.desktop && \
	rm -f eegview-AntNeuro-32EEG.desktop && \
	rm -f eegview-AntNeuro-64EEG.desktop && \
	rm -f CNBILoop-Close.desktop && \
	rm -f CNBIWheelchairVisualization.desktop && \
	rm -f CNBIMobileResting.desktop

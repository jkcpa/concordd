#
# Copyright (c) 2017 Robert Quattlebaum
# Portions Copyright (c) 2016 Nest Labs, Inc.
# All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

FROM ubuntu:trusty

RUN apt-get -y update \
	&& DEBIAN_FRONTEND=noninteractive \
			apt-get install -y -q --no-install-recommends \
				libglib2.0-dev \
				libdbus-1-dev \
				libdbus-1-dev \
				libboost-dev \
				libboost-signals-dev \
				libreadline-dev \
				libtool \
				autoconf-archive \
				dbus \
				xtables-addons-source \
				net-tools \
				usbutils \
				vim \
				man \
				bsdtar \
				gcc g++ \
				pkg-config

RUN apt-get -y update \
	&& DEBIAN_FRONTEND=noninteractive \
			apt-get install -y -q --no-install-recommends \
				autoconf \
				autoconf-archive \
				automake

#   Copyright IBM Corporation 2020
#
#   Licensed under the Apache License, Version 2.0 (the "License");
#   you may not use this file except in compliance with the License.
#   You may obtain a copy of the License at
#
#        http://www.apache.org/licenses/LICENSE-2.0
#
#   Unless required by applicable law or agreed to in writing, software
#   distributed under the License is distributed on an "AS IS" BASIS,
#   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#   See the License for the specific language governing permissions and
#   limitations under the License.

FROM registry.access.redhat.com/ubi8/ubi-minimal:latest
RUN microdnf update && microdnf install wget xz tar && microdnf clean all && \
    wget https://nodejs.org/dist/v16.16.0/node-v16.16.0-linux-x64.tar.xz && \
    tar -xJf node-v16.16.0-linux-x64.tar.xz && \
    mv node-v16.16.0-linux-x64 /node && \
    rm -f node-v16.16.0-linux-x64.tar.xz
ENV PATH="$PATH:/node/bin"
COPY . .
RUN npm install
EXPOSE 8080
CMD npm run start


THIS_DIR = $(GOPATH)/src/ex1
PROTO_FILE = $(THIS_DIR)/service.proto
PROTOC_FLAGS += -I $(GOPATH)/src
DEST_DIR = $(GOPATH)/src/ex1
PLUGINS=grpc

all:
	# generate bindings
	protoc --go_out=plugins=$(PLUGINS):$(DEST_DIR) $(PROTOC_FLAGS) $(PROTO_FILE)
	# generate templates
	go install github.com/moul/protoc-gen-gotemplate
	protoc -I. --gotemplate_out=template_dir=templates,debug=true,all=true:. service.proto 
	# run the example
	go install ex1/...
	


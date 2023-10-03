TARGET=../target
V1_DAR=$(TARGET)/V1.dar
V2_DAR=$(TARGET)/V2.dar

.PHONY: build
build: $(V1_DAR) $(V2_DAR)

$(V1_DAR): $(shell find . -name *.daml) V1/daml.yaml
	daml build --project-root V1/ --output $@

$(V2_DAR): $(V1_DAR) $(shell find . -name *.daml) V2/daml.yaml
	daml build --project-root V2/ --output $@

.PHONY: clean
clean:
	daml clean --project-root V1
	daml clean --project-root V2
	$(RM) -r $(V1_DAR) $(V2_DAR)

